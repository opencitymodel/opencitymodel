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
| [Alabama](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-feb/Alabama.html) | 102 | 451MB | 2035MB |
| [Alaska](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-feb/Alaska.html) | 6 | 23MB | 100MB |
| [Arizona](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-feb/Arizona.html) | 73 | 505MB | 2275MB |
| [Arkansas](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-feb/Arkansas.html) | 88 | 251MB | 1220MB |
| [California](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-feb/California.html) | 317 | 3253MB | 12164MB |
| [Colorado](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-feb/Colorado.html) | 95 | 375MB | 1772MB |
| [Connecticut](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-feb/Connecticut.html) | 34 | 233MB | 1012MB |
| [Delaware](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-feb/Delaware.html) | 10 | 69MB | 295MB |
| [DistrictofColumbia](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-feb/DistrictofColumbia.html) | 2 | 11MB | 51MB |
| [Florida](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-feb/Florida.html) | 209 | 1385MB | 6046MB |
| [Georgia](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-feb/Georgia.html) | 202 | 672MB | 3147MB |
| [Hawaii](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-feb/Hawaii.html) | 9 | 48MB | 215MB |
| [Idaho](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-feb/Idaho.html) | 52 | 155MB | 745MB |
| [Illinois](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-feb/Illinois.html) | 178 | 860MB | 3999MB |
| [Indiana](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-feb/Indiana.html) | 129 | 573MB | 2701MB |
| [Iowa](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-feb/Iowa.html) | 111 | 335MB | 1611MB |
| [Kansas](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-feb/Kansas.html) | 117 | 249MB | 1267MB |
| [Kentucky](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-feb/Kentucky.html) | 134 | 400MB | 1887MB |
| [Louisiana](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-feb/Louisiana.html) | 89 | 385MB | 1734MB |
| [Maine](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-feb/Maine.html) | 26 | 143MB | 618MB |
| [Maryland](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-feb/Maryland.html) | 55 | 303MB | 1373MB |
| [Massachusetts](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-feb/Massachusetts.html) | 57 | 399MB | 1732MB |
| [Michigan](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-feb/Michigan.html) | 165 | 878MB | 4060MB |
| [Minnesota](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-feb/Minnesota.html) | 120 | 503MB | 2342MB |
| [Mississippi](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-feb/Mississippi.html) | 89 | 258MB | 1226MB |
| [Missouri](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-feb/Missouri.html) | 149 | 544MB | 2538MB |
| [Montana](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-feb/Montana.html) | 62 | 125MB | 622MB |
| [Nebraska](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-feb/Nebraska.html) | 100 | 174MB | 903MB |
| [Nevada](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-feb/Nevada.html) | 34 | 224MB | 878MB |
| [NewHampshire](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-feb/NewHampshire.html) | 19 | 109MB | 479MB |
| [NewJersey](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-feb/NewJersey.html) | 71 | 459MB | 2064MB |
| [NewMexico](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-feb/NewMexico.html) | 43 | 191MB | 886MB |
| [NewYork](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-feb/NewYork.html) | 150 | 911MB | 4088MB |
| [NorthCarolina](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-feb/NorthCarolina.html) | 168 | 811MB | 3749MB |
| [NorthDakota](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-feb/NorthDakota.html) | 55 | 83MB | 451MB |
| [Ohio](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-feb/Ohio.html) | 174 | 986MB | 4504MB |
| [Oklahoma](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-feb/Oklahoma.html) | 98 | 369MB | 1745MB |
| [Oregon](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-feb/Oregon.html) | 67 | 343MB | 1566MB |
| [Pennsylvania](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-feb/Pennsylvania.html) | 156 | 928MB | 4135MB |
| [RhodeIsland](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-feb/RhodeIsland.html) | 11 | 76MB | 309MB |
| [SouthCarolina](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-feb/SouthCarolina.html) | 79 | 405MB | 1805MB |
| [SouthDakota](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-feb/SouthDakota.html) | 68 | 92MB | 506MB |
| [Tennessee](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-feb/Tennessee.html) | 126 | 547MB | 2471MB |
| [Texas](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-feb/Texas.html) | 415 | 1810MB | 8244MB |
| [Utah](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-feb/Utah.html) | 44 | 183MB | 858MB |
| [Vermont](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-feb/Vermont.html) | 15 | 64MB | 288MB |
| [Virginia](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-feb/Virginia.html) | 156 | 533MB | 2462MB |
| [Washington](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-feb/Washington.html) | 96 | 641MB | 2697MB |
| [WestVirginia](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-feb/WestVirginia.html) | 61 | 165MB | 813MB |
| [Wisconsin](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-feb/Wisconsin.html) | 115 | 554MB | 2543MB |
| [Wyoming](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-feb/Wyoming.html) | 25 | 64MB | 312MB |


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
