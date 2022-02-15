# Options for GIS Experts

If you are familiar with working with GIS data, this may be useful for you.


## Version Number

Current Version of the Landscaping plugin.

## Imported through Landscaping

Wheter the Landscape or World Composition found in the Level is imported through the plugin or not. This is set automatically and shouldn't be changed normally.

## Projections

After opening the Landscaping Plugin, a `LandscapingInfos` object is created in the scene. Select it in the World Outliner and have a look in the Details panel.
In the `Landscaping Expert` foldout, a property named `Root Projection` states the target projection which is used in the current level. It will be empty first and automatically determined on DTM or Shapefile import.

## Allowed DTM File Types

Landscaping is using [GDAL](https://gdal.org/) under the hood. It is tested to import GeoTiff, ASCII Info and HGT files properly. However, it should work with every driver built in with the GDAL library.

Changing the Allowed DTM file Types allows you to select other DTM files. A list with possible file formats can be found at [Raster drivers](https://gdal.org/drivers/raster/index.html).

> There is no guarantee, that other file types work. Trying to import other files than what GDAL supports will crash the Unreal Editor.

## Override Raster Data Scale

For special purpouses, if one wishes to create World Composition with a different scale than the real world scale, the Raster Data Scale can be overwritten with `Override Raster Data Scale`.
Raster Data Scale effects both, the scale of the final Landscape imported from DTM files and the points of the Shapefile.

> The scale of the resulting Landscape has always to be uniform, otherwise the collision will be screwed.

The base `Scale Factor` is only set after import of a Landscape or World Composition.
The scale of a single Landscape can of course always be changed through Unreal Engines native features.

## Vector Data Scale

Like Raster Data Scale, the points of the Shapefile can be scaled independently. The `Override Vector Data Scale` let's you specify at which scale the Vector Data should be imported.

> If you set `Override Vector Data Scale` the value of `Override Raster Data Scale` will be ignored for Shapefiles.

## Draw Vector Data Debug

After selecting files in the `Weightmaps and Landscape Material` dialog or in the `Import Roads, Railtracks, Rivers, etc.` section, the vector data is already loaded. To visualize it, check `Draw Vector Data Debug`. It will draw lines over the Landscape to preview, where the vector data from the Shapefile will be imported.

By changing `Override Vector Data Scale` the change of the scale will also be reflected by it.

It is possible to use the Gizmos to move the anchor of the shapefiles. Translation and Scale Gizmo can be used.

## Snap to Ground

Snap the vector point to the ground of the Landscape. This might kill framerate if huge shapefiles are imported.

## Debug Update Interval

To save performance, the update interval of the debug drawing can be controlled here.

## Bounds Delimiter

Not used yet.
