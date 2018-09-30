# Open City Model
Open City Model is an initiative to provide open [cityGML](https://www.citygml.org) data for all the buildings in the United States.  By using other open datasets such as [USBuildingFootprints](https://github.com/Microsoft/USBuildingFootprints) in conjunction with our own code and algorithms it is our goal to provide 3D geometries for US building inventory.

The project is currently in a *beta* release comprised of data for approximately 11 million buildings in the state of California.


# The Data

| State        | Files        | Size  |
| ------------ |-------------:| -----:|
| [California](http://ocm-citygml-beta.s3-website-us-east-1.amazonaws.com/California/) | 266          | 53GB |


# FAQ

### How can I read cityGML files?
There are a lot of great options on the [cityGML website](https://www.citygml.org/software/).  We like to use Azul for quick viewing of files and citygml4j for programmatic uses.

### What is included in the files?
The files currently contain building data and focus specifically on the 3D geometry of the building.  We also include a few useful attributes such as the area of the footprint, the measured height of the building, the US state & county (FIPS code).

### What units are used in the data?
The data is written using the epsg:3857 coordinate system for geo positions and all values are in meters.

### What is the level of detail (LOD) of the data?
All of the files contain only LOD1 buildings at present.  Our first goal is to get the best possible coverage of LOD1 for all of the buildings in the USA.  Once we feel comfortable with our LOD1 coverage then we are interested in shooting for LOD2, but we consider that a ways away.

### Will you be releasing more cityGML files in the future?
Our current plans include releasing files covering all buildings in the United States.  Beyond that we don't have any plans, but we are open to talking about it.


# License
This data is licensed by [BuildZero.Org](http://www.buildzero.org) under the [Open Data Commons Open Database License (ODbL)](https://opendatacommons.org/licenses/odbl/)
