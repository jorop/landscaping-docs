# Get Data

Landscaping supports raster data in various common formats and vector data in ESRI Shapefile format. The Shapefiles have to come with annotations which meet the specs of [geofabrik.de](https://download.geofabrik.de/).

## Raster Data

Landscaping can handle any GeoTiff rasterfile with height data (aka Digital Terrain Model, DTM) as well as HGT file format (SRTM1 and SRTM3 data) and ASCII Grid files.
Projection, pixelscale or resolution does not matter.
ASCII Grid files have to have a *.prj file associated which is normally the case if you download it somewhere.
For HGT files the filename must comply to the format NXXWYYY[.optional].hgt which is also normally the case. So please make sure not to rename an HGT file.

Sources for DTM files are for example:

- [NASA Earth Explorer](https://earthexplorer.usgs.gov/)
- [Viewfinder Panoramas](http://viewfinderpanoramas.org/dem3.html)

Better resolutions will also create more detailed landscapes in Unreal Engine 4. Search the web for the open data portal of your desired country. Often they offer 1 m or even better resolution GeoTiff rasters for free.

## Vector Data

While it is possible to import any Shapefile through Landscaping into Unreal Engine 4, the plugin is designed to work with [geofabrik.de](https://download.geofabrik.de/) annotated Shapefiles. It will allow you to generate weightmaps and spline based Actors.

After you downloaded the Shapefiles from geofabrik and unzipped the folder a collection of different aspects of the country can be found splitted into many files.

![Landscaping Tab](_media/ue4_landscaping_shapefile.jpg)

For weightmap generation following files are relevant:

- gis_osm_landuse_a_free_1.shp
- gis_osm_natural_a_free_1.shp
- gis_osm_water_a_free_1.shp

All this files contain POLYGONS, which is necessary to derive weightmaps.
Optionally, gis_osm_buildings_a_free_1.shp can also be used for weightmap generation, but not in conjunction with gis_osm_landuse_a_free_1.shp. However, using gis_osm_buildings_a_free_1.shp is not recommended for bigger landscapes (> 10 km²) because the runtime to generate the appropriate weightmaps will increase a lot.

For spline based Actors, following files are appropriate:

- gis_osm_railways_a_free_1.shp
- gis_osm_roads_a_free_1.shp
- gis_osm_waterways_a_free_1.shp

All this files contain LINESTRINGS, which is necessary to generate rivers, roads, etc.
Optionally, gis_osm_buildings_a_free_1.shp can also be used to procedurally generate buildings. For this purpose, one has to implement the interface IVectorActor in a Blueprint or in C++ with custom logic.
