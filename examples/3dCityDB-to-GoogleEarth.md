## Display a 3D model of any US city in Google Earth

This is an example of how you could use the Open City Model to view a 3D rendering of your city and perhaps gain a new perspective on where you live!  In this example we will start by loading a portion of the Open City Model (your choice) into the [3dCityDB](https://www.3dcitydb.org/) which provides a foundation for doing geospatial work with 3D city objects.  Once we've loaded some data int our database we'll export a KML visualization of the buildings which we can easily view and play with in Google Earth.

### Software Requirements

We try to keep the examples as simple as possible but the world of geospatial software is still fairly complex and it should be kept in mind that this example is meant for a more technical audience.

* [Java 8+](https://www.java.com/en/download/) - You'll need a recent version of Java available on your computer in order to run the Importer-Exporter tool provided as part of the 3dCityDB.
* [Docker](https://www.docker.com/get-started) - For the sake of simplicity this example uses Docker for running the actual 3dCityDB instance which is a Postgres/PostGIS database.

### I. Run 3dCityDB (via Docker)

This should be fairly straight forward as long as you have Docker running.  Simply run the following command to download the image and run a new container ...

```
docker run -dit --name citydb -p 5432:5432 -e "SRID=4326" -e "SRSNAME=urn:adv:crs:EPSG::4326" tumgis/3dcitydb-postgis
```

NOTE: this will attempt to map port 5432 in your new docker container to port 5432 on your computer, so you must be sure that port is unused.

### II. Install and launch 3dCityDB-Importer-Exporter application

The importer/exporter is a Java based desktop appliction which provides a nice UI for interacting with the data inside your 3dCityDB.

1. Head over to https://www.3dcitydb.org/3dcitydb/downloads/ and download the latest version of the application.
2. Execute the .jar file to launch the GUI installer.  On my Mac if I double-click the file I get a security warning, so I must right-click the file, then choose `Open With` > `Jar Launcher.app`
3. Follow the installer steps along the way and leave all the options at their defaults.  This is a standard installer with a language choice, a license to accept, and the option to pick where to install to.
4. Once the files are installed you can safely close the installer.
5. Now we want to launch the actual importer/exporter application by using the appropriate script in the `bin` folder of the location where you installed the files.  For example on my Mac I am launching `3DCityDB-Importer-Exporter/3dcitydb/bin/3DCityDB-Importer-Exporter` which I can simply double-click on in Finder.
6. If the importer/exporter is open and displaying on your desktop then you are good-to-go :+1:
