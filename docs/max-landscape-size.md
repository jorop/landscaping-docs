# Maximum Landscape Size

## Unreal Engine Requirements

Please refer to [System Requirements](https://docs.unrealengine.com/5.0/en-US/hardware-and-software-specifications-for-unreal-engine/) for Unreal Engine requirements.

## Bare Landscape Memory Requirements

Possibilities and limits when importing landscapes in Unreal Engine 5.0
For UE 5.0 32 km x 32 km is about the limit what can be edited on a up-to-date gaming PC with reasonable frame-rate.

Please note: the values are valid for UE 5.0 with 1 vertex per meter landscape resolution.
With UE 5.1 due to changed memory management, it is possible to import bigger landscapes.

This table gives a rough overview of the requirements when using Landscaping plugin and World Partition (only the Landscape, without Landscape Material, Foliage, etc.) with the whole Landscape loaded and a `Desired Max Landscape Size` of 16384:  

| Area         |      RAM    |  recommended | FPS |
|--------------|------------:|-------------:|----:|
| 100 km²      |    ~ 25 GB  |  32 GB       | 120 |
| 250 km²      |    ~ 40 GB  |  64 GB       | 120 |
| 1000 km²     |    ~ 70 GB  |  128 GB      |  50 |
| 2000 km²     |   ~ 120 GB  |  256 GB      |  20 |

These values are taken from a machine with 128 GB RAM, 12 Core CPU, RTX 3070Ti.  

From Landscaping 7.0 on there is also an optimized algorithm to import vast landscapes as World Partition at lower resolutions which look awesome. Which in consequence allowes for bigger import.  

The plugin can import larger areas as World Partition than through the native Unreal Landscape Importer by splitting the area into several landscapes. The size of a single Landscape is controlled by `Desired Max Landscape Size` in the `DTM Import Options` dialog.  
> While increasing the `Desired Max Landscape Size` will result in a better runtime performance, it will also need a lot more RAM on creation.  

## UE 5.1

From UE 5.1 the memory requirements are much lower.  
Please see this video for what is possible:  
[![Fill missing heightmap areas](https://img.youtube.com/vi/v39gdYNiB4s/0.jpg)](https://www.youtube.com/watch?v=v39gdYNiB4s)

## Recommendation

For performance reasons we recommend a maximum landscape size of 16 km x 16 km (256 km²). This also allows for Edit Layers to be activated. While it is possible to extend the area to very large amounts, multiple landscapes in one level will impact the framerate. In other words: a landscape with 32 km x 32 km (`Desired Max Landscape Size` of 32768) will still have a framerate of 120, but will also need a minimum of 128 GB RAM on import.
