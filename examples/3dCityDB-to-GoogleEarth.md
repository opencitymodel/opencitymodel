## Display a 3D model of any US city in Google Earth

This is an example of how you could use the Open City Model to view a 3D rendering of your city and perhaps gain a new perspective on where you live!  In this example we will start by loading a portion of the Open City Model (your choice) into the [3dCityDB](https://www.3dcitydb.org/) which provides a foundation for doing geospatial work with 3D city objects.  Once we've loaded some data int our database we'll export a KML visualization of the buildings which we can easily view and play with in Google Earth.

### Software Requirements

We try to keep the examples as simple as possible but the world of geospatial software is still fairly complex and it should be kept in mind that this example is meant for a more technical audience.

* [Java 8+](https://www.java.com/en/download/) - You'll need a recent version of Java available on your computer in order to run the Importer-Exporter tool provided as part of the 3dCityDB.
* [Docker](https://www.docker.com/get-started) - For the sake of simplicity this example uses Docker for running the actual 3dCityDB instance which is a Postgres/PostGIS database.

