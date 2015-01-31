---
title: Setting up a PostGIS database with OpenStreetMaps data
tags: blog
layout: post-layout
date: 2014-10-15
---

I'm currently working in a group for UW-Madison's [Internet of Things
Lab](http://www.iotlab.wisc.edu), we are making a Google Glass application that
can act as an "augmented reality tour" and give the wearer information on campus
buildings that they are currently looking at. For our first step, we needed a
way to store geographic information on all the university's buildings. After a
bit of research, I decided to populate a PostGIS database with data from the 
OpenStreetMaps project. The following is an excerpt from a write-up I made to
document the steps I took and explain them to my group members:

![Query image](http://i.imgur.com/qMeyRqi.jpg)

1. First, I spun up a virtual private server on [Digital
   Ocean](http://www.digitalocean.com).  VPS's are super nice, because you can
   mess around with them and if you break things too much, you just destroy it
   and start over again.

2. I then followed the steps given on the OpenStreetMap wiki on [installing
   PostGIS](http://wiki.openstreetmap.org/wiki/PostGIS/Installation) to get a
   PostgreSQL with the [PostGIS](http://postgis.net/) extension enabled.

3. Download the Madison OpenStreetMap data from the lovely folks at
   [Mapzen](https://mapzen.com/metro-extracts/) with a little `wget
   https://s3.amazonaws.com/metro-extracts.mapzen.com/madison_wisconsin.osm.pbf`
   
4. Use osm2pgsql to import osm data into the postgres database. The project's
   [readme on github](https://github.com/openstreetmap/osm2pgsql) has nice usage
   commands. I ended up running this command `osm2pgsql --create --database gis
   --cache-strategy sparse madison_wisconsin.osm.pbf` (Note: I needed to use
   sparse caching with the memory restrictions on the VM I made)

5. I ran this command. `select name, building, from planet_osm_polygon where
   building='university' order by name;` to get a list of all UW buildings.
   Really promising start! Thanks to all the nice open source stuff from osm,
   PostGIS, and others, getting this basic setup is rather painless. More work
   needs to be done to figure out how to do the "Field of View query" we are
   thinking of to return only the building the user is looking at from their
   GPS and compass heading, but I'm pretty optimistic right now. Some things to
   note: the coordinates from osm are in the 900913 projection, and will need
   to be transformed (using PostGIS's command ST_Transform) to a more familiar
   lat/long projection like 4326)
