# Maximum Landscape Size

## Unreal Engine Requirements

Please refer to [System Requirements](https://docs.unrealengine.com/5.0/en-US/hardware-and-software-specifications-for-unreal-engine/) for Unreal Engine requirements.

## Bare Landscape Memory Requirements

This table gives a rough overview of the requirements when using Landscaping plugin and World Partition (only the Landscape, without Landscape Material, Foliage, etc.) with the whole Landscape loaded and a [World Partition Max Landscape Size](settings.md?id=world-partition-max-landscape-size) of 16384:  

| Area         |      RAM    |  recommended | FPS |
|--------------|------------:|-------------:|----:|
| 100 km²      |    ~ 25 GB  |  32 GB       | 120 |
| 250 km²      |    ~ 40 GB  |  64 GB       | 120 |
| 1000 km²     |    ~ 70 GB  |  128 GB      |  50 |
| 2000 km²     |   ~ 120 GB  |  256 GB      |  20 |

These values are taken from a machine with 128 GB RAM, 12 Core CPU, RTX 3070Ti.  

The plugin can import larger areas as World Partition than through the native Unreal Landscape Importer by splitting the area into several landscapes. The size of a single Landscape is controlled by [World Partition Max Landscape Size](settings.md?id=world-partition-max-landscape-size).  
> While increasing the World Partition Max Landscape Size will result in a better runtime performance, it will also need a lot more RAM on creation.  

## Recommendation

For performance reasons we recommend a maximum landscape size of 16 km x 16 km (256 km²). This also allows for Edit Layers to be activated. While it is possible to extend the area to very large amounts, multiple landscapes in one level will impact the framerate. In other words: a landscape with 32 km x 32 km (World Partition Max Landscape Size of 32768) will still have a framerate of 120, but will also need a minimum of 128 GB RAM on import.
