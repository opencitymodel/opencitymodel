# Open City Model
Open City Model is an initiative to provide open [cityGML](https://www.citygml.org) data for all the buildings in the United States.  By using other open datasets such as [USBuildingFootprints](https://github.com/Microsoft/USBuildingFootprints) in conjunction with our own code and algorithms it is our goal to provide 3D geometries for US building inventory.

The project is currently in a *beta* release comprised of data for approximately 11 million buildings in the state of California. The full release for the US will contain 125 million buildings.


# The Data

Each US state has its own folder with all of its cityGML files.  The files for each state are futher separated by [US county](https://www.census.gov/geo/reference/codes/cou.html) and then split into files of 40k buildings to keep file sizes more manageable.

Within each folder you will find files of the format `<StateName>-<CountyCodeFIPS>-<FileNumber>.gml` so for example the file for San Francisco, Ca is California-06075-000.gml

| State        | Files        | Size (GML) | Size (JSON) |
| ------------ |-------------:| ----------:| -----------:|
| [Alabama](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jan/Alabama.html) | 102 | 474MB | 2091MB |
| [Alaska](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jan/Alaska.html) | 6 | 24MB | 103MB |
| [Arizona](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jan/Arizona.html) | 73 | 521MB | 2336MB |
| [Arkansas](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jan/Arkansas.html) | 88 | 267MB | 1255MB |
| [California](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jan/California.html) | 301 | 2357MB | 10159MB |
| [Colorado](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jan/Colorado.html) | 93 | 372MB | 1731MB |
| [Connecticut](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jan/Connecticut.html) | 34 | 236MB | 1044MB |
| [Delaware](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jan/Delaware.html) | 10 | 70MB | 303MB |
| [DistrictofColumbia](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jan/DistrictofColumbia.html) | 2 | 12MB | 52MB |
| [Florida](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jan/Florida.html) | 209 | 1431MB | 6213MB |
| [Georgia](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jan/Georgia.html) | 202 | 711MB | 3236MB |
| [Hawaii](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jan/Hawaii.html) | 9 | 49MB | 221MB |
| [Idaho](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jan/Idaho.html) | 52 | 158MB | 767MB |
| [Illinois](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jan/Illinois.html) | 178 | 897MB | 4121MB |
| [Indiana](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jan/Indiana.html) | 129 | 598MB | 2777MB |
| [Iowa](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jan/Iowa.html) | 111 | 349MB | 1660MB |
| [Kansas](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jan/Kansas.html) | 117 | 260MB | 1308MB |
| [Kentucky](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jan/Kentucky.html) | 134 | 423MB | 1945MB |
| [Louisiana](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jan/Louisiana.html) | 89 | 396MB | 1787MB |
| [Maine](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jan/Maine.html) | 26 | 147MB | 637MB |
| [Maryland](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jan/Maryland.html) | 55 | 324MB | 1409MB |
| [Massachusetts](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jan/Massachusetts.html) | 57 | 403MB | 1762MB |
| [Michigan](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jan/Michigan.html) | 165 | 914MB | 4179MB |
| [Minnesota](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jan/Minnesota.html) | 120 | 518MB | 2405MB |
| [Mississippi](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jan/Mississippi.html) | 89 | 267MB | 1258MB |
| [Missouri](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jan/Missouri.html) | 149 | 572MB | 2616MB |
| [Montana](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jan/Montana.html) | 62 | 131MB | 635MB |
| [Nebraska](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jan/Nebraska.html) | 100 | 181MB | 928MB |
| [Nevada](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jan/Nevada.html) | 34 | 229MB | 902MB |
| [NewHampshire](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jan/NewHampshire.html) | 19 | 110MB | 491MB |
| [NewJersey](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jan/NewJersey.html) | 71 | 486MB | 2127MB |
| [NewMexico](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jan/NewMexico.html) | 43 | 200MB | 909MB |
| [NewYork](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jan/NewYork.html) | 149 | 957MB | 4206MB |
| [NorthCarolina](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jan/NorthCarolina.html) | 168 | 875MB | 3854MB |
| [NorthDakota](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jan/NorthDakota.html) | 55 | 89MB | 460MB |
| [Ohio](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jan/Ohio.html) | 174 | 1036MB | 4633MB |
| [Oklahoma](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jan/Oklahoma.html) | 98 | 384MB | 1792MB |
| [Oregon](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jan/Oregon.html) | 67 | 347MB | 1605MB |
| [Pennsylvania](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jan/Pennsylvania.html) | 156 | 975MB | 4256MB |
| [RhodeIsland](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jan/RhodeIsland.html) | 11 | 77MB | 317MB |
| [SouthCarolina](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jan/SouthCarolina.html) | 79 | 427MB | 1859MB |
| [SouthDakota](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jan/SouthDakota.html) | 68 | 98MB | 517MB |
| [Tennessee](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jan/Tennessee.html) | 126 | 564MB | 2523MB |
| [Texas](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jan/Texas.html) | 415 | 1878MB | 8483MB |
| [Utah](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jan/Utah.html) | 44 | 190MB | 883MB |
| [Vermont](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jan/Vermont.html) | 15 | 68MB | 295MB |
| [Virginia](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jan/Virginia.html) | 158 | 554MB | 2514MB |
| [Washington](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jan/Washington.html) | 96 | 657MB | 2771MB |
| [WestVirginia](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jan/WestVirginia.html) | 61 | 181MB | 834MB |
| [Wisconsin](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jan/Wisconsin.html) | 115 | 582MB | 2619MB |
| [Wyoming](http://htmlpreview.github.io/?https://github.com/opencitymodel/opencitymodel/blob/master/releases/2019-jan/Wyoming.html) | 25 | 66MB | 319MB |


# FAQ - Technical

### How can I read cityGML files?
There are a lot of great options on the [cityGML website](https://www.citygml.org/software/).  We like to use Azul for quick viewing of files and citygml4j for programmatic uses.

### What is included in the files?
The files currently contain building data and focus specifically on the 3D geometry of the building.  We also include a few useful attributes such as the area of the footprint, the height of the building, the US state & county (FIPS code), and the [UBID](https://ubid.pnnl.gov/) (Universal Building ID).

### What units are used in the data?
The data is written using the epsg:3857 coordinate system for geo positions and all values are in meters.

### What is the level of detail (LOD) of the data?
All of the files contain only LOD1 buildings at present.  Our first goal is to get the best possible coverage of LOD1 for all of the buildings in the USA.  Once we feel comfortable with our LOD1 coverage then we are interested in shooting for LOD2, but we consider that a ways away.

### Can I access the files programmatically?
Certainly!  All of the files are available on S3 in the bucket `ocm-citygml-beta` so you can list the contents of that bucket using any s3 client to get the files that way if you wish.

### Will you be releasing more cityGML files in the future?
Our current plans include releasing files covering all buildings in the United States.  Beyond that we don't have any plans, but we are open to talking about it.

### How accurate are the building footprints used to create the CityGML?
The building footprints were created by Microsoft using high resolution imagery and advanced machine learning algorithms. Microsoft claims that the footprints in most cases are at least as accurate as those created through field digitization by hand in Open Street Maps. See Microsoft’s [USBuildingFootprints](https://github.com/Microsoft/USBuildingFootprints) for details.

### Are there plans for increasing the accuracy of building footprints?
We hope that a community-supported process for data contribution will emerge over time as it did with OSM, and perhaps even in conjunction with OSM. A building data validation and contribution process should include add/change/delete functions for a variety of core building data attributes including footprint, height, stories, etc. GIS-enabled smartphones, tablets, drones and other devices are increasingly providing field data capture to support 3D buildings data validation and enrichment functions.

### What is the data source for building heights in OCM?
The preliminary building heights included in the current beta release were generated with a simple regression analysis algorithm comparing building footprint areas with heights using a 4M buildings OSM dataset. It should be reasonably accurate across the vast majority of buildings with the exception of dense urban environments with tall, multistory buildings, i.e. skyscrapers.

### Are there plans for increasing the accuracy of building heights?
Yes. We are working on more sophisticated training data sets and algorithms. We welcome contributions to this effort. We also plan to incorporate “actual” building heights from other data sets like OSM when possible. Also see the notes above on improving the accuracy of core building attributes using field-collected data.

### What is a Universal Building ID (UBID) and why is it important?
[UBID](https://ubid.pnnl.gov/) is an initiative by the US Department of Energy (DOE) to establish a system for generating and maintaining unique ID’s for all buildings across the planet. The UBID algorithm generates a unique ID based on the geo-spatial location and form of a building footprint. A unique building ID will provide a universal indexing mechanism for the collection, linking and aggregation of building-centric data from disparate sources.

# FAQ - General

### What is CityGML?
CityGML is a data model (schema) for describing urban environments. CityGML describes urban objects like buildings, roads, bridges, trees, etc. in 3D geographical space. CityGML urban object data attribute classes include: Semantics, Geometry, Topology, and Appearance. CityGML is an open, international consensus standard with over fifteen years of cooperative development and use. It is recognized and supported by the [Open Source Geospatial Foundation](https://www.osgeo.org/)

Application Domain Extensions (ADE) exist for Energy, Noise, Utilities and other application domains, and new ADE’s are being developed. The ADE’s provide schemas that extend the CityGML model to include data attributes that support domain specific applications such as building energy modeling at building, district and city scale. Detailed information is available at [CityGML.org](https://www.citygml.org/).

### Why is CityGML important?
Urban environments are highly complex and require sophisticated software tools to enable proper analysis and design. A stable, tested, open, consensus standard urban data model is essential for effective and efficient software development, collaboration, sharing and scaling globally. Cities and districts world wide face daunting planning challenges in energy, GHG reduction, water, transportation, noise, pollution, etc.. CityGML provides the necessary data architecture for complex urban planning and modeling, and the open standard platform to enable efficient collaboration and sharing amongst stakeholders worldwide.

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
  * BuildZero.Org: [City Energy Explorer](https://ca.dev.buildzero.org/#), [Building Energy Designer](https://designer.dev.buildzero.org/)


### Why was the Open City Model (OCM) created?
Open Street Maps was the inspiration for the creation of the Open City Model. GIS data and software has evolved beyond the limits of 2D mapping applications. 3D applications including urban models for various use cases are in strong demand and evolving rapidly. OCM was created to accelerate the development and use of 3D urban models for critical applications related to climate action.

### What is the vision for evolution of the Open City Model?
We hope that establishing OCM as an Open Data platform using the consensus standard CityGML urban data model will accelerate development, collaboration and sharing. Time is of the essence for climate action. Other urban planning domains can certainly benefit. Bring on the “Smart City”!

### Who is BuildZero.Org?
[BuildZero.Org](http://www.buildzero.org/) is a 501(c)3 non-profit creating public-access digital infrastructure for climate action apps in local communities. BuildZero provides a free, open-standards-based, scalable platform of data and climate action apps. BuildZero is “social infrastructure” funded by social capital serving local governments, citizens, building professionals, and other public/private sector stakeholders.


# License
This data is licensed by [BuildZero.Org](http://www.buildzero.org) under the [Open Data Commons Open Database License (ODbL)](https://opendatacommons.org/licenses/odbl/)

# Contact
Feel free to create an issue via github or you can email us via `OpenCityModel at BuildZero.Org`
