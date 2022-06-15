# Landcover

Applying a Landscape Material and generating __weightmaps__ on the fly. The good thing about it: no preprocessing of data is needed. We only have to download some Shapefiles.

## Get it from the web

Landscaping is designed to work with OpenStreetMap Data Extracts from Geofabrik. [Download](https://download.geofabrik.de/) the Shapefiles from your country and extract the zip-file. For the example files please download the Shapefiles from `Austria` in Europe.

## Importing Shapefiles

> If you are working with World Composition: please __unload__ all tiles before proceeding  

When clicking on the `Open` button next to Landscape Material Settings a new window pops up. Hit the `Select` button and choose `gis_osm_landuse_a_free_1.shp` or multiple files (see [Get Data](get-data.md?id=vector-data)) from the extracted files. If others than the shapefiles from geofabrik.de are chosen, make sure it contains fclass attributes for the assignment later. It is possible to select several Shapefiles at once. It may take a few seconds until the file is read. After that, choose the Landscape Material in the next step.

> To reset the input simply close the Landscaping tab and open it again.  

![Landscape Material and Weightmaps](_media/ue4_landscaping_weightmaps.jpg)  

## Landscape Material

Pick a Landscape Material from your content folder. Please also see this topic for slopes of Landscape Auto-Materials and Z-Scale: [Override Z Scale of generated landscape](heights.md?id=override-z-scale-of-generated-landscapes)  

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

The generation of weightmaps can take time. Roughly it takes 10 seconds per km² per distinct landuse area. If the landscape is huge and has many distinct areas, this adds up. For example, an area in the alps with ~ 220 km² and moderate distinct areas took about 39 minutes to calculate. Another test with a ~ 650 km² world and a lot of small distinct areas took a little more than 3 hours and 30 minutes to finish. Of course it depends on the machine you are using, mainly on the number of cores of your CPU. So, if you plan to generate huge worlds, please consider this. All tests where performed with a AMD Ryzen 3 2600 CPU with 32 GB RAM. Still, this is a lot faster than every other method and it is very accurate.

## Next steps

After having the ground set, let's grow some bushes and trees: [Vegetation](vegetation.md?id=vegetation)  
Or lay a river in the riverbed: [Props](props.md?id=props)
