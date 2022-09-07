# LandscapingInfos Actor

After opening the `Landscaping Tab` an Actor called `LandscapingInfos` is created in the scene. The Actor can be selected like every Actor in the World Outliner in the Unreal Engine Editor.

In the Details Panel of the Unreal Engine Editor you can see different section belonging to Landscaping. They mainly hold metadata so that the `Landscaping Plugin` can do it's work properly. It's properties are described in the tooltip (hover with mouse cursor over property name).

> Please do not delete the `LandscapingInfos` Actor as long as you plan to work with the `Landscaping Plugin` in the editor.

The Actor is an Editor Only actor and will therefore automatically __not__ be included when packaging the project.

## Options in the Landscaping Section (Details Panel)

Select `LandscapingInfos`in the Outliner. Under `Landscaping` following options are provided.

## DTM

### Allowed DTM File Types

Landscaping is using [GDAL](https://gdal.org/) under the hood. It is tested to import GeoTiff, ASCII Info and HGT files properly. However, it should work with every driver built in with the GDAL library.

Changing the Allowed DTM file Types allows you to select other DTM files. A list with possible file formats can be found at [Raster drivers](https://gdal.org/drivers/raster/index.html).

> There is no guarantee, that other file types work. Trying to import other files than what GDAL supports will crash the Unreal Editor.

### Landscape Scale Factor

For special purpouses, if one wishes to create World Partition with a different scale than the real world scale, the Landscape Scale can be overwritten with `Landscape Scale Factor`.
Landscape Scale effects both, the scale of the final Landscape imported from DTM files and the points of the Shapefile.

> The internal calculated scale of the resulting Landscape will be multiplied with this value. E.g. if the value is set to 0.5 the resulting Landscape size will be halved.  

The scale of a single Landscape can of course always be changed through Unreal Engines native features. Changing it with unreal engine native features will however make it necessary to also change `Vector Data Scale` accordingly.  

### Use Precise Scale

Wheter to use precise scale (float). Default is false. -> Please note using precise scale can lead to gaps between Landscapes. Can be set to true savely if only a single Landscape without World Partition is imported.  

## Shapefile

### Vector Data Scale

Like Landscape Scale, the points of the Shapefile can be scaled independently. The `Vector Data Scale` let's you specify at which scale the Vector Data should be imported.

> If you set `Vector Data Scale` the value of `Landscape Scale Factor` will be ignored for shapefiles.

### Draw Vector Data Debug

After selecting shapefiles in the `Weightmaps and Landscape Material` dialog or in the `Import Roads, Railtracks, Rivers, etc.` section, the vector data is already loaded. To visualize it, set `Draw Vector Data Debug` to true. It will draw lines over the Landscape to preview, where the vector data from the Shapefile will be imported.

By changing `Vector Data Scale` the change of the scale will also be reflected by it.

It is possible to use the Gizmos to move the anchor of the shapefiles. Translation and Scale Gizmo can be used. Inputs of `XYOffset` and `Vector Data Scale` serve the same purpose.  

### Snap to Ground

Snap the vector point to the ground of the Landscape. This might kill framerate if huge shapefiles are imported.

### Debug Update Interval

To save performance, the update interval of the debug drawing can be controlled here.

### XYOffset

Offset of the Bounds. The offset specifies the Origin of any vectordata imported (shapefiles for Roads etc. or shapefiles for Weightmaps). Also it moves the vectordata crop area  which is visualized with a dark-orange rectangle.
