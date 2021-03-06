# Custom Logic on Vector Data

With a C++ class or Blueprint implementing the `LandscapingVectorInterface`, custom logic on importing LINESTRINGS, POLYGONS and POINTS from a Shapefile can be fired off.

The `Landscaping Plugin` will instantiate the Blueprint at the first point of the LINESTRING, POLYGON or POINT and will call `OnVectorData` which can be implemented as `OnVectorData_Event` in the Blueprint. `OnVectorData` will give you a struct of `FVectorData`:

- TArray < FVector > Points -> Points, which make up the shape
- FString FeatureClass -> OSM feature class (may be empty if other shapefiles than from geofabrik.de are loaded)
- FString Name -> Name of the shape (may be empty)
- FString GeometryName -> Type of the shape, e.g. LINESTRING, POLYGON or POINT
- bool bShow -> used for internal debugging purposes only

After calling `OnVectorData` the plugin will move on to the next shape, instantiating the Blueprint at the first point of the LINESTRING, POLYGON or POINT, call `OnVectorData` like above and so on.

> This is a convinient way to set up custom logic and can be used to construct buildings etc.

An example how this works and how to use it in a Blueprint is shipped with the plugin in the Content/Blueprints folder: `BP_VectorDataExample`.
The example will instantiate a Point Light on the location of every vector data point.

To use your custom Blueprint, select it under `Blueprint` in the `Import Roads, Railtracks, Rivers, etc.` section.
