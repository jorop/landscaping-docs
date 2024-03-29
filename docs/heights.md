# Heights

Making a huge tiled landscape is as easy as making a single landscape.

> Please make sure that you have enough RAM when importing huge areas!

## Choosing input files

> To reset the input simply close the Landscaping tab and open it again.  

In order to create a tiled landscape, you can choose one or multiple files in the file selection dialog.  
In UE5 it is possible to choose [World Partition](#world-partition) and specify the grid size to segment a Landscape into LandscapeStreamingProxies. Depending on the `Max Desired Tile Size`, the tiles for the landscape will be created on the fly.  

> A tiled landscape can be created from a single file or from multiple files

For both, `World Partition` and non-World-Partitioned Worlds, the `Desired Max Tile Size` will control the maximum size of a single landscape.  
There are only two things to consider:
> The file size of a single file can be 2 GB max.  
> System memory must keep up with the size of the landscape -> see [Max Landscape Size](max-landscape-size.md?id=maximum-landscape-size).

## Options

The Landscaping plugin allows you to set the area to import with the `Corners as Bounding Box` input or in UE5 directly in the DTM Import Options Dialog.  
For downloading heightmaps from Mapbox using the `Landscaping Mapbox` plugin, the import area is also specified here by simply select the desired area to import. (Please note, that Mapbox only has data for land areas, not sea areas).

## Import Area (optional)

> In UE5 (from plugin version 7.0 on), you can simply view and/or select the area on the integrated browser, you do not have to copy-paste the bounding box.

![UE5 integrated Map Selection](_media/ue5_integrated_browser.jpg)  

> The following step is only necessary for plugin version lower 7.0 and UE4 users  
Here it is possible to limit the area which should be imported. To get an idea what is imported please click on `Show Map`:  
![Show Map](_media/ue4_landscaping_dtm_huge.jpg)  
> The following step is only necessary for plugin version lower 7.0 and UE4 users  
A browser window opens and shows the area which encompasses the heightdata files:  
![Import DTM files](_media/ue4_landscaping_dtm_map.jpg)  
> The following step is only necessary for plugin version lower 7.0 and UE4 users  
Select edit on the toolbar on the right side and drag the rectangle corners until the desired import area is covered:
![Import DTM files](_media/ue4_landscaping_dtm_map2.jpg)  
> When importing DTM files, the import area has to be smaller than the original area!
> The following step is only necessary for plugin version lower 7.0 and UE4 users  
After clicking save, the map centers on the new area. Select the coordinates in the adress bar of the browser and copy them (Ctrl+C):
![Import DTM files](_media/ue4_landscaping_dtm_map3.jpg)
> The following step is only necessary for plugin version lower 7.0 and UE4 users  
Back in Unreal Engine Editor paste the coordinates (Ctrl+V) in the `Corners as Bounding Box` text input and hit `Enter`:  
![Limit Import Area](_media/ue4_landscaping_dtm_limit_area.jpg)

The info text should now show the new extent of the area. Only this part of the heightdata will be imported.

## Location and Scale

### Location

The X and Y Location of the Landscape (first Tile, if multiple tiles are generated). The pivot of a Landscape is on the top-left corner. With `Center` the Landscape is positioned, so that it is centered in the UE coordinate system. If X and Y are set to 0, the Landscape will expand from 0 to the bottom and to the right.

### High Detail Z Scale

The vertical scale will be calculated automatically to perserve the most detail, using the maximum available Unreal Engine Landscape vertical resolution. Defaults to `true`. This should be set to `false` when extending or updating heightmaps.  

### Custom Landscape Z Scale

Use this for areas with low altitude difference or when extending or updating the landscape. Defaults to `100`. For understanding the technical reason for this, please consult [Calculating Heightmap Z Scale](https://docs.unrealengine.com/5.1/en-US/landscape-technical-guide-in-unreal-engine/).  

## Landscape Generation Options

### Import as Mesh

Import as Procedural Mesh instead of Landscape (e.g. for a distance mesh). The Procedural Mesh can afterwards converted to a nanite mesh with a button in the details panel of the Procedural Mesh.

### Force square Landscapes

Regardles of the selection, force a square landscape. This enables to export/import weightmaps in the native UE Landscape Edit Mode (e.g. for editing weightmaps in another program) This is not affecting the real world scale (blank areas will appear, but no distortion will happen).

### Auto calculate Landscape

Calculate Sections and Components of the Landscape to import automatically given the extents of the input file. Uncheck to give custom specs (see properties below). This is not affecting the real world scale.

### Section Size

Please see [Landscape Technical Guide](https://docs.unrealengine.com/5.2/en-US/landscape-technical-guide-in-unreal-engine/)

### Sections per Component

Please see [Landscape Technical Guide](https://docs.unrealengine.com/5.2/en-US/landscape-technical-guide-in-unreal-engine/)

### Number of Components

Please see [Landscape Technical Guide](https://docs.unrealengine.com/5.2/en-US/landscape-technical-guide-in-unreal-engine/)

### Landscape Resolution

Shows the expected Landscape Resolution in vertices

### Desired Max Tile Size

The maximum size of a created Landscape of World Partition or single Landscape imports in meter (Landscape or Mesh). If the size of a single Landscape exceeds this size, it will be split, and multiple Landscape Actors are created in the level. This is the size of the resulting Landscape in Unreal Engine, not the max size or resolution of a source file (like GeoTiff, etc.). E.g. a value of 32768 will import landscapes with maximum 32 km length or width. 32768 will need at least 128 GB of RAM.

> `Desired Max Landscape Size` defaults to `8192` meter.  
> Edit Layers can only be activated if the value is `16384` or below.

Tip: you can type aritmetic expressions into the input box like `8192*2` or `8192/2`

### World Partition Grid Size

Grid size for the World Partition Landscape.  

> Please make sure you use the `Empty Open World` Template when enabling World Partition and check `Enable Streaming` in World Settings.

### Mapbox Zoom Level

Set the Zoom Level for Mapbox heightdata imports (see [Mapbox Documentation](mapbox.md)). Only available with Mapbox Extension.

### Use native Raster Pixel Size

Use the pixel size from the imported heightmap. Uncheck to use custom Raster Pixel Size below.

### Custom Raster Pixel Size

Set a custom pixel size for the imported heightmap. The heightmap will be resampled to this pixel size (meter/pixel) before import. Lower values will result in more pixel per meter (more vertices in a Landscape/Mesh).

### Resample to First Tile

Will import all imported DTM files (or Mapbox height data) to the resolution of the first imported DTM of the level enabling seamless worlds with no gaps. This might lead to up- or downsampling depending on the first imported DTM.  

### Smooth Steps

Apply gaussian blur on the height data before importing the landscape. This will smooth raster data with low resolution.  
0 means, no smoothing will happen.
For Mapbox imports the recommended value is 1 for mountain terrain, and 2 for flat terrain.  

## Smooth Edges

When creating multiple Landscapes from DTM files (or Mapbox) in a level, this __should be disabled__ to have seamless connections on the edges of each Landscape. For a single Landscape this can be enabled savely.  

## Landscape Update Options

> This options is only meaningful, if you try to fill missing data with mapbox, otherwise a faster way to fill missing data is just selecting (`Select DTM Files` button) all heightmap data (geotiff-, ascii- or hgt-files, also mixed is possible) and let them merge on import automatically.

### Update Landscape

Wheter to update an already imported area (area must be a Landscape)

### Only fill missing

Only update areas with no data -> Please see the youtube video [![Fill missing heightmap areas](https://img.youtube.com/vi/2kkmY9Hi1qg/0.jpg)](https://www.youtube.com/watch?v=2kkmY9Hi1qg)

### Minimum height tolarance

The distance between the lowest valid point of an already imported landscape and the bottom flat area (no data area) in centimeter

## Landscape Material

Assign a Landscape Material which will be applied to the imported Landscape.

## Default Layer

The Landscape Material's default paint layer, with which the landscape will be filled.  
> Some Landscape Materials include a __Invisible__ layer, which makes the Landscape invisible.

## General

It is possible to import raster files with different projections and resolutions and they will be aligned properly. You do not have to worry about it. It is even possible to import GeoTiff, ASCII and HGT files toghether. However: files with different resolutions (meter per pixel) will be result in seams (where more detailed and less details heightmaps meet).

> Landscaping can handle overlapping files

Datasets handed over to the `Landscaping Plugin` may intersect, they will be merged and result in a seamless landscape or World Composition.

> Temporary files are created upon import in the folder defined in `Project Settings -> Plugins -> Landscaping -> Cache Directory`. After import these files can be used for other applications or deleted.  
> If the setting `Use in Memory Files`is selected, only files from mapbox will be saved to disk.

## Next Steps

Make the gray checkered landscape colorful with [Weightmaps / Paint Layers](landcover.md?id=landcover)
