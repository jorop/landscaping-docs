# Get Data

Landscaping supports raster data in various common formats (GeoTiff, ASCII, HGT, GeoPackage) and vector data in ESRI Shapefile format and other (see below). The Shapefiles for weightmaps should come with annotations which meet the specs of [geofabrik.de](https://download.geofabrik.de/). Shapefiles for spline based or other Actors do not necessarily need to be from geofabrik.de. These annotations are derived from OpenStreetMap, so other Vector data will work as well. It it does not, please see [Add fclass to shapefile](landcover.md?id=add-fclass-to-shapefile)

## Mapbox

With the extension [Landscaping Mapbox](https://www.unrealengine.com/marketplace/en-US/product/landscaping-mapbox) heightmap tiles from Mapbox can easily be imported.
Therefore only the extents (bounding box) of the area must be pasted into the [DTM import Options](heights.md?id=import-area-optional) dialog. The heightmaps will be downloaded automatically and the Landscape / World Composition / World Partition will be created.  
Please make sure to provide your Mapbox API key in `Project Settings -> Plugins -> Landscaping Mapbox`.  
Alternativley, you can provide your own Raster Data - see next section.

## Raster Data

Landscaping can handle any GeoTiff rasterfile with height data (aka Digital Terrain Model, DTM or Digital Elevation Model, DEM) as well as HGT file format (SRTM1 and SRTM3 data), ASCII Grid files and GeoPackage (.gpkg) files with height data.
Projection, pixelscale or resolution does not matter.  
ASCII Grid files have to have a *.prj file associated which is normally the case if you download it somewhere.  
For HGT files the filename must comply to the format NXXWYYY[.optional].hgt which is also normally the case. So please make sure the HGT filename confirms to this convention.

Sources for DTM files are for example:

- [OpenDEM](https://www.opendem.info/opendemsearcher.html)
- [NASA Earth Explorer](https://earthexplorer.usgs.gov/)
- [Viewfinder Panoramas](http://www.viewfinderpanoramas.org/Coverage%20map%20viewfinderpanoramas_org3.htm)
- [OpenTopography](https://portal.opentopography.org/raster?opentopoID=OTSRTM.082015.4326.1)
- [USGS](https://www.sciencebase.gov/catalog/item/4f552e93e4b018de15819c51)

Better resolutions will also create more detailed landscapes in Unreal Engine. __Search the web for the open data portal of your desired country to get better resolutions.__

> In general resolution from 0.5 meter per pixel until 5 meter per pixel will generate smooth terrains. The less meter per pixel the better.

### Important

> Please make sure you understand the data you are trying to import. Read the description of the heightdata file on the website where you are downloading it and think about how big the landscape will be. E.g. importing a 10500 x 8600 pixel GeoTiff with a resolution of 8 meter per pixel will result in a 5780 km² landscape. You can limit the import area in the [DTM Import Options](heights.md?id=options). Importing huge areas might exhaust your system memory and Unreal Engine will crash. Unreal Engine 4 needs about 20 GB RAM per 1000 km². For requirements regarding UE5 see [Max Landscape Size](max-landscape-size.md?id=maximum-landscape-size)  

It is possible to have a look at the data before importing. [QGIS](https://qgis.org/) is a free tool which can be used to see how the data looks like before importing it.

## Vector Data

The plugin supports following vector data types:

- ESRI Shapefile (.shp)
- GEOJSON (.json,.geojson,.geojsons,.geojsonl)
- OSM OpenSteetmap (.osm,.osm.pbr)
- Mapbox Vector data (through Landscaping Mapbox plugin)

While it is possible to import any Vector data (Shapefile, GeoJSON, GeoPackage with vector data) through Landscaping into Unreal Engine, the plugin was originally designed to work with [geofabrik.de](https://download.geofabrik.de/) annotated Shapefiles. It will allow you to generate weightmaps, spline based Actors and any other Actor. Please see [Add fclass to shapefile](landcover.md?id=add-fclass-to-shapefile) for how to add annotations to other vector data which is missing these annotations.  

After you downloaded the Shapefiles from geofabrik and unzipped the folder a collection of different aspects of the country can be found splitted into many files.

![Landscaping Tab](_media/ue4_landscaping_shapefile.jpg)

For weightmap generation following files are relevant:

- gis_osm_landuse_a_free_1.shp
- gis_osm_natural_a_free_1.shp
- gis_osm_water_a_free_1.shp

All this files contain POLYGONS, which is necessary to derive weightmaps. The 'a' in the filename stands for area - please make sure only select this kind of files for weightmap generation!
Optionally, gis_osm_buildings_a_free_1.shp can also be used for weightmap generation, but not in conjunction with gis_osm_landuse_a_free_1.shp. However, using gis_osm_buildings_a_free_1.shp is not recommended for bigger landscapes (> 10 km²) because the runtime to generate the appropriate weightmaps will increase a lot.

For spline based Actors, all shapefiles will work. To setup custom logic for generating Actors, see [LandscapingVectorInterface](landscapingvectorinterface.md) to implement the interface in a Blueprint or in C++.
