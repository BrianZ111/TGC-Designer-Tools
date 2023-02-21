# TGC-Designer-Tools Documentation [ver. 0.3.2.1]

BrianZ111's fork of chadrockey's TGC-Designer-Tools

[Download Releases](https://github.com/BrianZ111/TGC-Designer-Tools/releases)\
[Report Issues](https://github.com/BrianZ111/TGC-Designer-Tools/issues) > Please include steps required to recreate issue and post screenshots as needed.

## Handling of OSM Files

I highly encourage everybody to continue using the OSM server to do golf linework when it aligns with OpenStreetMap's goals (mainly in drawing existing real courses).  Making highly accurate linework available to the public offers numerous benefits.  It allows people to get started quickly in making new versions of courses for current or future games.  It also benefits the open source OSM project and those who use it for maps.

This update is for other situations where either the OpenStreetMap community does not take kindly to your changes because they are not relevant to the map service (such as no longer existing courses or fictional courses) or you need to avoid sharing the linework with the public, such as if you are working on renderings or plans for future real golf course construction projects. 

Use of drawing tools is out of scope for this document.  I only mention some below to help point you in the right direction when looking for instructions online on how to create OSM files.

* [JOSM](https://josm.openstreetmap.de/) is a free desktop utility specifically designed for OSM.  It features built in satellite image sources and can download or upload OSM server data. [Plugins](https://josm.openstreetmap.de/wiki/Help/Preferences/Plugins) such as [PicLayer](https://wiki.openstreetmap.org/wiki/JOSM/Plugins/PicLayer) allow you to [use custom images](https://josm.openstreetmap.de/wiki/Help/Plugin/PicLayer).
* Alternatively, you can draw using your favorite CAD or GIS software.  If your software does not save in OSM format, [QGIS](https://www.qgis.org/) is free GIS software that can work with and convert a variety of formats including OSM data through the use of plugins.  I personally use [QCAD](https://www.qcad.org/) and [Global Mapper](https://www.bluemarblegeo.com/global-mapper/) for drawing and converting.

The actual use of OSM files in TGC-Designer-Tools is pretty straight forward.  The process remains the same except that when processing LiDAR there are now two radio buttons.  OSM server uses the OSM server data as before while OSM file allows you to provide a file instead.  If you choose OSM file, when you click the button to start you now receive two successive dialog boxes.  The first is to choose the folder location of your LiDAR files as before, and the second is to choose the OSM file.

On the Import Terrain and Features tab there are also now two check boxes at the top for importing the OpenStreetMap linework and heightmap.  Unchecking one of these allows you to only import one or the other instead of both.  Under the OpenStreeMap category there are again the radio button choices of OSM server and OSM file.  If you choose OSM file, when you click the button to start you are again prompted twice, first for the heightmap folder and second for the OSM file.

If importing elevation data, leaving the OSM Only EPSG textbox blank defaults to the EPSG code entered when the LiDAR data was processed.  If importing only OpenStreetMap linework, enter an EPSG in this textbox that is appropriate for the geographic location you drew your linework at to minimize map projection distortion of your work.  If you are unsure, use [Projestions](https://projest.io/ns/) to help you choose.  It is as simple as placing a pin on the map and choosing a few parameters.  Projections with EPSG codes are then displayed, sorted from best to worst for that location.

## LiDAR Trees on Background Terrain

I added one other feature unrelated to OSM files.  In Chad's version, when pulling tree data from LiDAR and using it to plant the course, you could not include background terrain in the automated planting.  On the Import Terrain and Features tab, if you choose to add trees from LiDAR, an additional checkbox now exists to add trees to the background terrain as well.  Most of the time this is useful for automating filling out the course but you may bump into resource issues in the game if the background area is large and heavily forested.
