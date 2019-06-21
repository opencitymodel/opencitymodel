# Open City Model
Open City Model is an initiative to provide open [cityGML](https://www.citygml.org) data for all the buildings in the United States.  By combining other open datasets such as [USBuildingFootprints](https://github.com/Microsoft/USBuildingFootprints) together with our own code and algorithms it is our goal to provide 3D geometries for every building in the United States.

This data contains roughly 125 million buildings.


# The Data

The data is provided via AWS S3 in the bucket `opencitymodel`.  We include two data formats: gml ([CityGML](https://www.citygml.org)) and json ([CityJSON](https://www.cityjson.org/)) which are identical in content and purely vary in their structure.  Within the folder for a data format each US state has its own folder with all of its files.  The files for each US state are futher separated by [US county](https://www.census.gov/geo/reference/codes/cou.html) and then partitioned into files of 40k buildings to keep file sizes more manageable.  Please note that the GML files are zip compressed to minimize download sizes.

The full path to a single file looks like ..

`https://s3.amazonaws.com/opencitymodel/<data-version>/<file-format>/<StateName>/<CountyCodeFIPS>/<StateName>-<CountyCodeFIPS>-<FileNumber>.[zip|json]`

We also provide some easier to navigate file indexes for each state.  If you are familiar with accessing AWS S3 directly then you can simply use the AWS tools to list and download files from the `opencitymodel` bucket directly.

| State        | Files        | Size (GML compressed) | Size (JSON) |
| ------------ |-------------:| ----------:| -----------:|
| [Alabama](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jun/Alabama.html) | 102 | 495MB | 2253MB |
| [Alaska](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jun/Alaska.html) | 31 | 26MB | 122MB |
| [Arizona](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jun/Arizona.html) | 75 | 552MB | 2555MB |
| [Arkansas](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jun/Arkansas.html) | 88 | 282MB | 1334MB |
| [California](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jun/California.html) | 342 | 3632MB | 13955MB |
| [Colorado](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jun/Colorado.html) | 97 | 443MB | 2079MB |
| [Connecticut](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jun/Connecticut.html) | 34 | 246MB | 1116MB |
| [Delaware](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jun/Delaware.html) | 10 | 72MB | 323MB |
| [DistrictofColumbia](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jun/DistrictofColumbia.html) | 5 | 48MB | 195MB |
| [Florida](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jun/Florida.html) | 215 | 1573MB | 6924MB |
| [Georgia](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jun/Georgia.html) | 206 | 771MB | 3574MB |
| [Hawaii](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jun/Hawaii.html) | 10 | 58MB | 262MB |
| [Idaho](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jun/Idaho.html) | 52 | 161MB | 802MB |
| [Illinois](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jun/Illinois.html) | 191 | 1025MB | 4758MB |
| [Indiana](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jun/Indiana.html) | 131 | 616MB | 2920MB |
| [Iowa](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jun/Iowa.html) | 111 | 365MB | 1750MB |
| [Kansas](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jun/Kansas.html) | 118 | 268MB | 1371MB |
| [Kentucky](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jun/Kentucky.html) | 139 | 529MB | 2395MB |
| [Louisiana](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jun/Louisiana.html) | 91 | 427MB | 1946MB |
| [Maine](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jun/Maine.html) | 29 | 153MB | 683MB |
| [Maryland](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jun/Maryland.html) | 68 | 535MB | 2284MB |
| [Massachusetts](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jun/Massachusetts.html) | 72 | 683MB | 2856MB |
| [Michigan](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jun/Michigan.html) | 166 | 936MB | 4384MB |
| [Minnesota](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jun/Minnesota.html) | 121 | 563MB | 2649MB |
| [Mississippi](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jun/Mississippi.html) | 93 | 304MB | 1449MB |
| [Missouri](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jun/Missouri.html) | 149 | 591MB | 2765MB |
| [Montana](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jun/Montana.html) | 62 | 134MB | 668MB |
| [Nebraska](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jun/Nebraska.html) | 100 | 192MB | 1002MB |
| [Nevada](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jun/Nevada.html) | 35 | 238MB | 970MB |
| [NewHampshire](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jun/NewHampshire.html) | 20 | 122MB | 539MB |
| [NewJersey](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jun/NewJersey.html) | 77 | 515MB | 2312MB |
| [NewMexico](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jun/NewMexico.html) | 45 | 212MB | 986MB |
| [NewYork](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jun/NewYork.html) | 170 | 1231MB | 5386MB |
| [NorthCarolina](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jun/NorthCarolina.html) | 170 | 943MB | 4256MB |
| [NorthDakota](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jun/NorthDakota.html) | 55 | 106MB | 531MB |
| [Ohio](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jun/Ohio.html) | 178 | 1101MB | 5008MB |
| [Oklahoma](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jun/Oklahoma.html) | 99 | 396MB | 1899MB |
| [Oregon](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jun/Oregon.html) | 70 | 417MB | 1911MB |
| [Pennsylvania](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jun/Pennsylvania.html) | 160 | 1027MB | 4609MB |
| [RhodeIsland](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jun/RhodeIsland.html) | 11 | 81MB | 343MB |
| [SouthCarolina](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jun/SouthCarolina.html) | 79 | 440MB | 1964MB |
| [SouthDakota](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jun/SouthDakota.html) | 68 | 101MB | 542MB |
| [Tennessee](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jun/Tennessee.html) | 128 | 591MB | 2710MB |
| [Texas](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jun/Texas.html) | 424 | 2102MB | 9625MB |
| [Utah](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jun/Utah.html) | 45 | 216MB | 995MB |
| [Vermont](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jun/Vermont.html) | 15 | 70MB | 314MB |
| [Virginia](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jun/Virginia.html) | 162 | 678MB | 3078MB |
| [Washington](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jun/Washington.html) | 101 | 693MB | 2967MB |
| [WestVirginia](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jun/WestVirginia.html) | 61 | 186MB | 884MB |
| [Wisconsin](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jun/Wisconsin.html) | 123 | 699MB | 3134MB |
| [Wyoming](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jun/Wyoming.html) | 25 | 74MB | 349MB |


# Source Datasets

Open City Model is fundamentally a data pipeline.  Our goal is simply to piece together the many individual open datasets describing building geometries and produce a single unified view of that data.  As such, we are extremely grateful to the folks who are producing the data that goes into Open City Model, which is listed here.  We are always looking to add in more source data, so if you have a recommendation then post an issue and let us know!

| Source        | Buildings (approx)        |
| ------------ |-------------:|
| [MS USBuildingFootprints](https://github.com/microsoft/USBuildingFootprints) | 125m |
| [MS Building Footprints (2017)](https://wiki.openstreetmap.org/wiki/Microsoft_Building_Footprint_Data) | 9.8m |
| [Open Street Map](https://www.openstreetmap.org/) | 28.9m |
| [LA County LARIAC4 (2014)](https://egis3.lacounty.gov/dataportal/2016/11/03/countywide-building-outlines-2014-update-public-domain-release/) | 3.1m |


# FAQ - Technical

### How can I read cityGML files?
There are a lot of great options on the [cityGML website](https://www.citygml.org/software/) as well as the [cityJSON website](https://www.cityjson.org/en/latest/software/).

### What is included in the files?
The files currently contain building data and focus specifically on the 3D geometry of the building.  We also include a few useful attributes such as the area of the footprint, the height of the building, the US state & county (FIPS code), and the [UBID](https://ubid.pnnl.gov/) (Universal Building ID).

### What units are used in the data?
The data is written using the epsg:4979 coordinate system for geo positions.  This means that all of the 2D coordinates use WGS84 lat/lon values in degrees and the 3D coordinate is in meters.

### What is the level of detail (LOD) of the data?
All of the files contain only LOD1 buildings at present.  Our first goal is to get the best possible coverage of LOD1 for all of the buildings in the USA.  Once we feel comfortable with our LOD1 coverage then we are interested in LOD2, but we consider that a ways away.

### Can I access the files programmatically?
Certainly!  All of the files are available on S3 in the bucket `opencitymodel` so you can list the contents of that bucket using any s3 client to get the files that way if you wish.

### Will you be releasing more cityGML files in the future?
Our current plans include releasing files covering all buildings in the United States.  Beyond that we don't have any plans, but we are open to talking about it.

### How accurate are the building footprints used?
We gather footprints from various sources, so the accuracy depends on the source.  Our goal is to provide the best possible accuracy while still providing full coverage of all buildings.

Currently the majority of the building footprints were created by Microsoft using high resolution imagery and advanced machine learning algorithms. Microsoft claims that the footprints in most cases are at least as accurate as those created through field digitization by hand in Open Street Maps. See Microsoft’s [USBuildingFootprints](https://github.com/Microsoft/USBuildingFootprints) for details.

The source of each footprint is attributed in the data.

### What is the data source for building heights in OCM?
Wherever possible we attempt to use data with measured building heights.  When that is not possible we use machine learning to estimate the height of the remaining buildings.

Currently the modeled building heights were generated with a simple regression analysis algorithm comparing building footprint areas with heights using a 4M buildings OSM dataset. It should be reasonably accurate across the vast majority of buildings with the exception of dense urban environments with tall, multistory buildings, i.e. skyscrapers.

The source of the building height for each footprint is attributed in the data.

### Are there plans for increasing the accuracy of building heights?
Yes. We are working on more sophisticated training data sets and algorithms. We welcome contributions to this effort. We also plan to incorporate additional measured building heights from other data sets like OSM when possible.

### What is a Universal Building ID (UBID) and why is it important?
[UBID](https://ubid.pnnl.gov/) is an initiative by the US Department of Energy (DOE) to establish a system for generating and maintaining unique ID’s for all buildings across the planet. The UBID algorithm generates a unique ID based on the geo-spatial location and form of a building footprint. A unique building ID will provide a universal indexing mechanism for the collection, linking and aggregation of building-centric data from disparate sources.

# FAQ - General

### What is CityGML?
CityGML is a data model (schema) for describing urban environments. CityGML describes urban objects like buildings, roads, bridges, trees, etc. in 3D geographical space. CityGML urban object data attribute classes include: Semantics, Geometry, Topology, and Appearance. CityGML is an open, international consensus standard with over fifteen years of cooperative development and use. It is recognized and supported by the [Open Source Geospatial Foundation](https://www.osgeo.org/)

Application Domain Extensions (ADE) exist for Energy, Noise, Utilities and other application domains, and new ADE’s are being developed. The ADE’s provide schemas that extend the CityGML model to include data attributes that support domain specific applications such as building energy modeling at building, district and city scale. Detailed information is available at [CityGML.org](https://www.citygml.org/).

### Why is CityGML important?
Urban environments are highly complex and require sophisticated software tools to enable proper analysis and design. A stable, tested, open, consensus standard urban data model is essential for effective and efficient software development, collaboration, sharing and scaling globally. Cities and districts world wide face daunting planning challenges in energy, GHG reduction, water, transportation, noise, pollution, etc. CityGML provides the necessary data architecture for complex urban planning and modeling, and the open standard platform to enable efficient collaboration and sharing amongst stakeholders worldwide.

### Are there other open consensus urban data models like CityGML?
No. To our knowledge CityGML is the global de facto standard for 3D, geo-spatially-enabled urban models. The European Union has incorporated CityGML within its Spatial Data Infrastructure plan, Inspire.

ESRI, the leading private sector provider of GIS software solutions for governments and industry worldwide, has 3D urban data models. However, they are proprietary, not open consensus standards. They require the use of ESRI software, for example, ArcGIS.

### What software currently supports the CityGML data model?
- ESRI GIS software recognizes CityGML along with other open GIS data standards and provides tools for importing/exporting CityGML data sets. Therefore CityGML urban models can be imported and used in ESRI applications. Conversely, ESRI applications can export urban models as CityGML for use with other software.

- AutoDesk, RevIt and most other mainstream Building Information Modeling (BIM) software tools recognize CityGML and provide import/export tools to support it.

- [Safe Software](https://www.safe.com/) FME data extract/transform/load software supports CityGML.

- [Virtual City Systems](https://www.virtualcitysystems.de/en/) is a leading provider of software tools for use with CityGML.

- [CesiumJS](https://cesiumjs.org/) is an Open Source javascript library for creating geospatial applications that render 3D visualizations in a web browser including 3D CityGML models. [Cesium.com](https://cesium.com/) provides content and authoring services for creation and streaming of 3D tilesets for rendering visualizations in web browsers using CesiumJS.

- See the [CityGML.org](https://www.citygml.org/) website for more information.

### Who is using CityGML?
- Many European countries including: UK, Germany, Austria, France, Switzerland, Netherlands, Belgium, Sweden, Finland, Poland, and more with a variety of applications
- European Union: specified for Spatial Data Infrastructure
- International Building Performance Simulation Association (IBPSA): next generation energy modeling tools
- Lawrence Berkeley National Laboratory (LBNL): urban scale energy retrofit analysis (CityBES)
- BuildZero.Org: building energy planning, design and modeling
- New York
- Montreal, Canada
- Singapore

### What kind of applications use CityGML?
- Citizen/stakeholder engagement and reference
  * [Berlin Economic Atlas](https://www.businesslocationcenter.de/wab/maps/main/?lang=en#/)
  * [Smarter Together.eu](https://www.smarter-together.eu/)

- Urban modeling from individual, to district to city scale...energy, utility, noise, etc.
  * European Research Institutes and Universities
  * US: [Open City Model](https://github.com/opencitymodel/)

- Urban scale building energy retrofit analysis
  * LBNL: [CityBES](https://citybes.lbl.gov/)

- Next generation building, district and urban scale energy modeling tools:
  * [IBPSA Project One](https://ibpsa.github.io/project1/)

- Building Energy Planning, Design and Modeling
  * BuildZero.Org


### Why was the Open City Model (OCM) created?
Open Street Maps was the inspiration for the creation of the Open City Model. 3D applications including urban models for various use cases are in strong demand and evolving rapidly. OCM was created to accelerate the development and use of 3D urban models for critical applications related to climate action.

### What is the vision for evolution of the Open City Model?
We hope that establishing OCM as an Open Data platform using the consensus standard CityGML urban data model will accelerate development, collaboration and sharing. Time is of the essence for climate action. Other urban planning domains can certainly benefit. Bring on the “Smart City”!

### Who is BuildZero.Org?
[BuildZero.Org](http://www.buildzero.org/) is a 501(c)3 non-profit creating public-access digital infrastructure for climate action apps in local communities. BuildZero provides a free, open-standards-based, scalable platform of data and climate action apps. BuildZero is “social infrastructure” funded by social capital serving local governments, citizens, building professionals, and other public/private sector stakeholders.


# License
This data is licensed by [BuildZero.Org](http://www.buildzero.org) under the [Open Data Commons Open Database License (ODbL)](https://opendatacommons.org/licenses/odbl/)

# Contact
Feel free to create an issue via github or you can email us via `OpenCityModel at BuildZero.Org`
