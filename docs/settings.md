# Settings

Landscaping does provide settings which are saved per project and can be found in `Project Settings -> Plugins -> Landscaping`.  
For Settings of __Landscaping Mapbox__ see [Landscaping Mapbox](mapbox.md?id=mapbox)

## Cache Directory

When importing heightdata (DTM files), intermediate files are generated. They are necessary to circumvent the 2 GB import restriction from Unreal Engine. Please make sure it is set to a writable directory. The plugin will try to create the directory, if it does not exist already.

> The Cache Directory defaults to `C:/Temp/Landscaping`

## World Partition Max Landscape Size

The maximum size of a created Landscape in World Partition. If the size of a single Landscape exceeds this size, it will be split, and multiple Landscape Actors are created in the level. This is the size of the resulting Landscape in Unreal engine, not the max size or resolution of a source file (like GeoTiff, etc.).

> The World Partition Max Landscape Size defaults to `8192`.  
> Tip: you can type aritmetic operation into the input box like `8192*2` or `8192/2`

![Landscaping Settings](_media/ue5_landscaping_settings.jpg)