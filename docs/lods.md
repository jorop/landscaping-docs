# Landscape LODs

First things first:

> Always backup your project before generating Landscape LODs

Landscape LODs is the last and final feature of the `Landscaping Plugin`.
It is pretty much a duplicate of the LOD Settings found in World Composition. So why is it here?
Well: if you have a huge world, then you have to load every level by hand and assign the LOD settings for this level or the couple of levels you have loaded. This works well as long as you can load all levels at once. But when the world gets to big to load all levels, assigning LOD settings is not so much fun anymore (was it ever?).
This section stores the LOD settings and does the tedious job of loading every level and generating the LODs for you.

See [World Browser](https://docs.unrealengine.com/en-US/BuildingWorlds/LevelStreaming/WorldBrowser/index.html) for more infos about LOD Settings.

> The LOD Settings are stored in the LandscapingInfos Actor in the Persistent Level. Please keep the Actor as long as you plan to update or change Landscape LODs.
