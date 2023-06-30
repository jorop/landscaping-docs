# Landcover

Applying a Landscape Material and generating __weightmaps__ on the fly. The good thing about it: no preprocessing of data is needed. We only have to download some Shapefiles.

> Unreal Engine paints the Landscape Material Layers according to the underlying resolution of the heightmap. The default is 1 vertex per meter (pixel/meter). The import resolution can be adjusted before import in [DTM Options](heights.md?id=custom-raster-pixel-size).

## Get it from the web

Landscaping is designed to work with OpenStreetMap Data Extracts from Geofabrik. Other Shapefiles (also GeoJSON and GeoPackage) will also work with the right annotations (see [Add fclass to shapefile](landcover.md?id=add-fclass-to-shapefile)).  
[Download](https://download.geofabrik.de/) the Shapefiles from your country and extract the zip-file. For the example files please download the Shapefiles from [Austria](https://download.geofabrik.de/europe/austria.html) in Europe.

## Importing Vectordata

> If you are working with UE4 World Composition: please __unload__ all tiles before proceeding  

When clicking on the `Open` button next to Landscape Material Settings a new window pops up. Hit the `Select` button and choose `gis_osm_landuse_a_free_1.shp` or multiple files (see [Get Data](get-data.md?id=vector-data)) from the extracted files. If others than the shapefiles from geofabrik.de are chosen, make sure it contains fclass attributes for the assignment later. It is possible to select several Shapefiles at once. It may take a few seconds until the file is read. After that, choose the Landscape Material in the next step.

> In Mapbox, the desired `Mapbox Zoom Level` should be set before select.

![Landscape Material and Weightmaps](_media/ue4_landscaping_weightmaps.jpg)  

## Landscape Material

Pick a Landscape Material from your content folder.

## Material Layers

A whole bunch of checkboxes will appear. So what is that about? Well, here we assign the layers of the Landscape Material to one or multiple landcover types aka landuses. The `Landuse Types` are read from the flcass attribute of the shapes in the shapefile. One Material Layer can have one or more landuse types but not vice versa. Notice, that the column of the landcover type gets grayed out, if you assign it to a Material Layer. If a Material Layer has the same name as the landcover type, it will appear already selected. It is not mandatory, to select every landuse type nor Material Layer. Weightmaps will only be created for those landuses, which are assigned to a Material Layer. For everything else, the Default Layer is used.

> All Material Layers in use are generated as weightblended

## Default Layer

The Default Layer is used everywhere, on the landscape, if there is no other landuse type assigned.

## Noise Texture

Next to the layer name there are options to assign a noise texture, choose the noise textures color channel and set the minimum weight of the layer in the appropriate landuse type as well as the tiling of the noise texture. The noise texture will create variation blended with the default layer. There are two sample perlin noise textures in the content folder of the plugin.  

See how noise textures work:  

[![Bake noise into Weightmaps](https://img.youtube.com/vi/UpqGl-J4WRo/0.jpg)](https://youtube.com/UpqGl-J4WRo)  

## Wait for it

When pleased with the mapping hit the `Replace` Button. It will erase the current weightmaps and replace them with the new settings.

Depending on the extent of the landscape and wether it is tiled or not, it will take several minutes (e.g. 100 km2) to hours (e.g. on a 1000 km2 landscape) until all calculations are finished and you can see the result.

## Add fclass to shapefile

If other shapefile used than this from geofabrik.de, it is possible to add an fclass attribute to the shapefile.

### Steps to add fclass attribute to shapefile

Add an attribute to an shapefile, using QGIS:  
1.) Load shapefile in QGIS  
2.) Right click it in Layers Tab and choose `Open Attribute Table`  
3.) Click `Edit` (pencil icon) and then `New Column` (Ctrl+W)  
4.) Fill out with  __Name=fclass, Type=string, Length= 64__  
5.) `Select All` (Ctrl+A)  
6.) Click `Multiediting Mode` (next to pencil icon) and type the value for the attribute (e.g. lake)  
7.) `Save` and close the dialog  
8.) Export the shapefile (right click on layer -> `Export...`)  
Then it will be compatible.

## Notes on runtime

The generation of weightmaps can take time. Especially if there are a lot of distinctive layers with small areas.

## Next steps

After having the ground set, let's grow some bushes and trees: [Foliage](vegetation.md?id=vegetation)  
Or lay a river in the riverbed: [Splines / Actors / Blueprints](props.md?id=props)
