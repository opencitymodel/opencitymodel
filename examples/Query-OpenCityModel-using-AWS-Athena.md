## Running queries on Open City Model using AWS Athena

[AWS Athena](https://aws.amazon.com/athena/) provides a great option for running queries against the Open City Model if your use case has an analytical need.  In this example we'll explore how you can setup Athena to query the Open City Model data directly where it lives, without the need to download it.

### Requirements

The only thing you need to run this example is an AWS account :smiley:

### I. Setup AWS Athena with Open City Model data for querying

The first thing we need to do is log in to AWS and navigate to the [AWS Athena Console](https://console.aws.amazon.com/athena/home).  From here we will define a basic schema representing the Open City Model data that we want to be able to query from Athena.

NOTE: all of these steps simply involve running the provided SQL in the Athena `Query Editor` tab.

1. Create a new `database` in Athena to represent Open City Model data.

```
CREATE DATABASE opencitymodel;
```

2. Define a `table` representing the Open City Model data that we want to access

In this example we will specifically target Open City Model data for the state of California.

```
CREATE EXTERNAL TABLE IF NOT EXISTS opencitymodel.california (
  `type` string,
  `version` string,
  `metadata` string,
  `cityobjects` string,
  `vertices` string
)
ROW FORMAT SERDE 'org.openx.data.jsonserde.JsonSerDe'
WITH SERDEPROPERTIES (
  'serialization.format' = '1'
) LOCATION 's3://opencitymodel/2019-jan/json/California/'
TBLPROPERTIES ('has_encrypted_data'='false');
```

![CreateTable](https://s3.amazonaws.com/static.opencitymodel.org/Query-OpenCityModel-using-AWS-Athena/CreateTable.png)

3. Define a `view` of our Open City Model data for easier querying

The Open City Model data we are going to query is in the CityJSON format and we want to do a very small transform on that data to make it more natural to run SQL queries against.

```
CREATE OR REPLACE VIEW opencitymodel.buildings AS
SELECT
  id,
  CAST(json_extract(bldg, '$.attributes.latitude') AS DOUBLE) AS lat,
  CAST(json_extract(bldg, '$.attributes.longitude') AS DOUBLE) AS lon,
  CAST(json_extract(bldg, '$.attributes.measuredheight') AS DOUBLE) AS height,
  CAST(json_extract(bldg, '$.attributes.area') AS DOUBLE) AS area,
  CAST(json_extract(bldg, '$.attributes.state') AS VARCHAR) AS state,
  CAST(json_extract(bldg, '$.attributes.county') AS VARCHAR) AS county,
  CAST(json_extract(bldg, '$.attributes.mgrs') AS VARCHAR) AS mgrs,
  CAST(json_extract(bldg, '$.attributes.ubid') AS VARCHAR) AS ubid,
  CAST(json_extract(bldg, '$.attributes.height_source') AS VARCHAR) AS height_source,
  CAST(json_extract(bldg, '$.attributes.fp_source') AS VARCHAR) AS fp_source
FROM opencitymodel.california
CROSS JOIN UNNEST(CAST(json_extract(cityobjects, '$') AS MAP(VARCHAR,JSON))) AS bldgs(id, bldg)
```

### II. Run queries against Open City Model

Now we get to the fun part.  With our schema established we can now simply run any queries that we want and Athena handles the heavy lifting.

1. Simple query to see the data

This is just a simple one to get us going and validate everything is working.  We'll simply list a random 10 buildings so get get a sense for what is included in the data.

```
SELECT * FROM opencitymodel.buildings LIMIT 10;
```

![QuerySimple](https://s3.amazonaws.com/static.opencitymodel.org/Query-OpenCityModel-using-AWS-Athena/QuerySimple.png)

2. Export a list all buildings in a given lat/lon bounding box

In this example we use a simple geospatial query to find the tallest buildings that are within a given bounding box and then we could decide to export that data into a CSV file if we wanted.

In this example we are looking at the buildings in a small neighborhood of San Francisco, Ca.

```
SELECT id, height, area, lat, lon
FROM buildings
WHERE lat BETWEEN 37.800921453    AND 37.8047694146
  AND lon BETWEEN -122.4090803069 AND -122.4028448283
ORDER BY height DESC;
```

![QueryBoundingBox](https://s3.amazonaws.com/static.opencitymodel.org/Query-OpenCityModel-using-AWS-Athena/QueryBoundingBox.png)

3. Calculate the total surface area (in hectares) used by buildings in each California county

We can also run some interesting aggregations based on attributes such as building height or area.  In this case we query to determine how much land area is used for buildings in each of California's counties.

```
SELECT county, round(sum(area)/10000) as area_hectares
FROM buildings
WHERE state = 'California'
GROUP BY county
ORDER BY area_hectares;
```
![QueryBuildingAreas](https://s3.amazonaws.com/static.opencitymodel.org/Query-OpenCityModel-using-AWS-Athena/QueryBuildingAreas.png)

From the results we can see that that California has a pretty wide spectrum of land use with Los Angeles county using a massive 63.8k hectares of land for buildings while just a bit farther north Alpine county has a meager 29 hectares of land for buildings.