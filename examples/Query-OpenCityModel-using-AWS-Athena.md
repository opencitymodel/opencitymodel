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

2. Define a `table` representing the Open City Model buildings data that we want to access

```
CREATE EXTERNAL TABLE `opencitymodel.jun2019`(
  `hash` string,
  `ubid` string,
  `grid` string,
  `lat` double,
  `lon` double,
  `area` double,
  `height` double,
  `height_source` string,
  `height_predict` double,
  `fp` string,
  `fp_source` string)
PARTITIONED BY (
  `state` string,
  `county` string)
ROW FORMAT SERDE
  'org.apache.hadoop.hive.ql.io.parquet.serde.ParquetHiveSerDe'
STORED AS INPUTFORMAT
  'org.apache.hadoop.hive.ql.io.parquet.MapredParquetInputFormat'
OUTPUTFORMAT
  'org.apache.hadoop.hive.ql.io.parquet.MapredParquetOutputFormat'
LOCATION
  's3://opencitymodel/2019-jun/parquet/'
TBLPROPERTIES (
  'parquet.compress'='SNAPPY',
  'has_encrypted_data'='false')

```

![CreateTable](https://s3.amazonaws.com/static.opencitymodel.org/Query-OpenCityModel-using-AWS-Athena/CreateTable.png)

3. Add our table partitions to Athena

Our data is partitioned by `state` and `county` to make it optimal for querying by region if you are not interested in looking at the entire USA.  This step simply informs Athena about what specific partitions exist so it can optimize data access for our queries when we run them.  You'll have to be a bit patient with this step because it can take several minutes (10m to be more precise).

```
MSCK REPAIR TABLE opencitymodel.jun2019
```

![AddPartitions](https://s3.amazonaws.com/static.opencitymodel.org/Query-OpenCityModel-using-AWS-Athena/AddPartitions.png)


### II. Run queries against Open City Model

Now we get to the fun part.  With our schema established we can now simply run any queries that we want and Athena handles the heavy lifting.

1. Simple query to see the data

This is just a simple one to get us going and validate everything is working.  We'll simply list a random 10 buildings to get a sense for what is included in the data.

```
SELECT * FROM opencitymodel.jun2019 LIMIT 10;
```

![QuerySimple](https://s3.amazonaws.com/static.opencitymodel.org/Query-OpenCityModel-using-AWS-Athena/QuerySimple.png)

2. Export a list all buildings in a given lat/lon bounding box

In this example we use a simple geospatial query to find the tallest buildings that are within a given bounding box and then we could decide to export that data into a CSV file if we wanted.

In this example we are looking at the buildings in a small neighborhood of San Francisco, Ca.

```
SELECT ubid, height, area, lat, lon
FROM opencitymodel.jun2019
WHERE lat BETWEEN 37.800921453    AND 37.8047694146
  AND lon BETWEEN -122.4090803069 AND -122.4028448283
  AND state = 'California'
  AND county = '06075'
ORDER BY height DESC;
```

![QueryBoundingBox](https://s3.amazonaws.com/static.opencitymodel.org/Query-OpenCityModel-using-AWS-Athena/QueryBoundingBox.png)

3. Calculate the total surface area (in hectares) used by buildings in each California county

We can also run some interesting aggregations based on attributes such as building height or area.  In this case we query to determine how much land area is used for buildings in each of California's counties.

```
SELECT county, round(sum(area)/10000) as area_hectares
FROM opencitymodel.jun2019
WHERE state = 'California'
GROUP BY county
ORDER BY area_hectares;
```

![QueryBuildingAreas](https://s3.amazonaws.com/static.opencitymodel.org/Query-OpenCityModel-using-AWS-Athena/QueryBuildingAreas.png)

From the results we can see that that California has a pretty wide spectrum of land use with Los Angeles county using a massive 69.2k hectares of land for buildings while just a bit farther north Alpine county has a meager 34 hectares of land for buildings.