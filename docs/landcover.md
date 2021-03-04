# Landcover

Applying a Landscape Material and generating weightmaps on the fly. The good thing about it: no preprocessing of data is needed. We only have to download some shapefiles.

## Get it from the web

A good resource are the OpenStreetMap Data Extracts from Geofabrik. [Download](https://download.geofabrik.de/) the Shapefiles from your country and extract the zip-file.

## Importing Shapefiles

When clicking on the `Open` button next to Landscape Material Settings a new window pops up. Hit the `Select` button and choose `gis_osm_landuse_a_free_1.shp` from the extracted files. It may take a few seconds until the file is read. After that, choose the Landscape Material in the next step or choose another shapefile. I recommend water and waterways, so that the ground can be set accordingly. It is also possible to select several shapefiles at once.

## Landscape Material

Pick a Landscape Material from your content folder. I like the Brushify Landscape Material. But every other Landscape Material is fine as well.

## Material Layers

A whole bunch of checkboxes will appear. So what is that about? Here we assign the Layers of the Landscape Material to one or multiple landcover types aka landuses. One Material Layer can have one or more landcover types but not vice versa. Notice, that the column of the landcover type gets grayed out, if you assign it to a Material Layer. If a Material Layer has the same name as the landcover type, it will be already selected.

## Wait for it

When pleased with the mapping close the Landscape Material and Weightmaps Window and click the `Import` button in the `Import Landscape` section. Depending on the extent of the landscape and wether it is tiled or not, it will take several minutes until all calculations are finished and you can see the result. Grass, forest ground, riverbeds and maybe beaches?

## Next steps

After having the ground set, let's grow some bushes and trees: [Vegetation](vegetation.md?id=vegetation)  
Or lay a river in the riverbed: [Props](props.md?id=props)
