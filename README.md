# Intro

My experiments with Geo-related server-side/client-side infrastructure. Slightly modified
(use Leaflet, proxy OpenStreetMap) original tutorial
(http://blog.perrygeo.net/2012/02/24/utfgrids-with-openlayers-and-tilestache/).

# Overview

This is an example of using TileStache, Mapnik and releated
infrastructure to set-up a server which renders image tiles
defined in shapefile, together with utfgrid json interactivity.
Leaflet client-side demo included.

# Install (Ubuntu)

```
sudo add-apt-repository ppa:mapnik/v2.2.0
sudo apt-get install libmapnik libmapnik-dev mapnik-utils python-mapnik
sudo pip install -U PIL modestmaps simplejson werkzeug
```

**Important**

Download TileStache from https://github.com/migurski/TileStache into `./tilestache` directory.

Download map shapefiles from https://github.com/migurski/TileStache/tree/master/examples/sample_data into `./map` directory.

Start client and backend servers

* ./run_server.sh
* ./client/run_client_server.sh

and visit [http://localhost:8000/client](http://localhost:8000/client)

# Use your own map and shapefiles

Edit `stylemap.xml`, update `<Parameter name="file">` for your own shapefile
and use appropriate attribute name to render colors.

Also use your preferred map tiles url in `tilestache.cfg` in
section under layers.world_osm.

In `tilestache.cfg`, use appropriate shapefile fields to be exported
for utfgrid interactivity.

