# Troubleshooting

## Changing Levels

When changing levels, the plugin may not detect the new level which is neccessary to save the metadata. Please close the `Landscaping Tab` and open it again. Thank you.

## Edges of the landscape

Due to the transformation of the input data, on areas, where no data is found the height is set to 0. Therefore, steep edges on the Landscape or World Composition outher border occur. Normally, this is not a problem, because who cares about the end of the world?  
Anyway - there are 2 options to mitigate this, if it is a problem for your project:

- The steep edges can easily be fixed within the native Unreal Engine Landscape Mode Sculpting Tools
- If your input data uses meter as unit, you may uncheck `Use OSM Projection` (not recommended)

## Missing Tiles

When importing a Tiled Landscape you will maybe notice, that there are a couple of the enumerated Tiles missing. Good news: they are not really missing. They just did have no data and where therefore not imported at all. If you need flat tiles with all heights set to 0, you can easily add them within World Composition.

## Crashes

If the Unreal Editor crashes on import, it may due to corrupted input data. Please send the data to `support@ludicdrive.com` to verify if it is a bug in the plugin or if the input data is to blame. Thank you.

## Accuracy

The `Landscaping Plugin` gives it's best to translate GIS data to Unreal Engine. Still, on bigger areas, the real world and the Unreal Engine Landscape can be significantly off. This can also be the case for weightmaps. It depends heavily on the input data, and cannot be fixed entirely. However, if you come accross such a problem, please read the [GIS Expert](gis-expert.md) section of this documentation. If you still having trouble, please contact `support@ludicdrive.com`. Thank you.
