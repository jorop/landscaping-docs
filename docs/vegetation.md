# Vegetation

Leverage Unreal Engines Procedural Foliage Tool to let accelarate foliage creation.  
> Please enable `Procedural Foliage` in `Edit -> Editor Preferences` to use this feature.

## Automation

This feature helps to populate World Composition / World Partition worlds with procedural foliage. It loads every World Composition Level, spawns the foliage and then saves and unloads it. For World Partition see [Enable Large Worlds](settings.md?id=enable-large-worlds)

## Procedural Foliage

In order for this feature to work, one has to prepare a [Procedural Foliage Spawner](https://docs.unrealengine.com/en-US/BuildingWorlds/OpenWorldTools/ProceduralFoliage/QuickStart/index.html). A `Procedural Foliage Spawner` is mandatory for creating automated plants and trees and also rocks and stones etc. on a landscape with Landscaping.

![Open World Automation](_media/ue5_landscaping_openworld.jpg)

## Options

> UE4: Please unload all World Composition tiles before proceeding
> UE5: Please make sure the part of the World Partition you want to spawn foliage is loaded

### Foliage Spawner

Assign a Procedural Foliage Spawner here.

### Remove Existing Foliage Volumes

This will remove any Procedural Foliage Volumes and all InstancedFoliageActors from the level.

### Reuse Existing Foliage Volumes

This option will update the volumes found in a level.

### Add New Foliage Volumes

When checked, will add the Foliage Spawner as new Procedural Foliage Volumes.

### Use Streaming Proxy Bounds

Will use the bounds of the Landscape Streaming Proxies (in World Partition worlds) instead of the bounds of the Landscapes. The Procedural Foliage Volumes will then be smaller which leads to faster generation of procedural foliage. Could often lead to volumes which do not match but are bigger than the bounds of the Landscape Streaming Proxy.

### Spawn Foliage

Whether to spawn foliage right after creating the Procedural Foliage Volume. Unchecked will only create the Volumes.  
Only use this option on smaller areas. For bigger areas, uncheck this and after hitting `Create / Spawn` select the Procedural Foliage Volumes in the Outliner, and click on `Resimulate` in the details panel.  

> Some of the checkboxes will be automatically deselect if another option is checked  

If everything is unchecked, nothing will happen when hitting the `Create` button.

> UE4: Please make sure to unload all Levels of a UE4 World Composition (except the Persistent Level) in the Unreal Engine 4 `Levels` tab before hitting `Create`
> UE5: Please make sure the part of the World Partition you want to spawn foliage is loaded
