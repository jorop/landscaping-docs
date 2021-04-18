# Custom Logic on Vector Data

With a C++ class or Blueprint implementing the IVectorActor interface, custom logic on importing LINESTRINGS, POLYGONS and POINTS can be fired off.

To use your custom Blueprint, select it under `Blueprint` in the `Import Roads, Railtracks, Rivers, etc.` section.

The `Landscaping Plugin` will instantiate the Blueprint at the first point of the LINESTRING, POLYGON or POINT and will call `SetVectorData`. `SetVectorData` will give you an array of FVectorData:

- TArray < FVector > Points -> Points, which make up the shape
- FString FeatureClass -> OSM feature class
- FString Name -> Name of the shape (may be empty)
- FString GeometryName -> Type of the shape, e.g. LINESTRING, POLYGON or POINT
- bool bShow -> used for internal debugging purposes only

After calling `SetVectorData` the plugin will move on to the next shape, instantiating the Blueprint at the first point of the LINESTRING, POLYGON or POINT, call `SetVectorData` like above and so on.

> This is a convinient way to set up custom logic and can be used to construct buildings etc.
