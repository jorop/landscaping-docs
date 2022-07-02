# Changelog

Changelog for the documentation see: [The Landscaping Docs on Github](https://github.com/jorop/landscaping-docs)

## Version 5.7

- feature: choose CRS mode in settings

## Version 5.6

- feature: bake noise into weightmaps (UE5)  

## Version 5.5

- feature: added 'Use Precise Scale' to allow for float scale instead of integer - please note, this could lead to tiny gaps between landscapes
- bugfix: paint layer UI partly disabled after opting in
- bugfix: weightmaps layer mapping checkboxes aligning
- bugfix: actors not painting layers on spawn and values not filled in
- change: actor labels keep original name of blueprint
- change: auxillary actors are flagged as editor only
- change: landscape scale will be set independently for x and y property (in LandscapingInfos `Override Raster Data Scale` is deprecated in favour of `Override Landscape Scale`)
- change: added tooltips to LandscapingInfos properties

## Version 5.4

- feature: change start and end width of spline mesh after creation in details tab

## Version 5.3

- feature: Procedural Foliage Spawner automation for UE5
- bugfix: XYOffset should be same value after re-opening level
- bugfix: missing interface check when selecting `Actor` in `Import Shapefiles` section could lead to crash

## Version 5.2

- feature: change Landscape Material's default paint layer on DTM import
- feature: override z scale of generated landscape on import
- bugfix: LandscapeVecterInterface stopped after first linestring was created  

## Version 5.1

- feature: settings for World Partition Max Landscape Size

## Version 5.0

- feature: extend landscape (World Partition)
- change: World Partition cell unloading while importing larger areas or shapefiles (UE5)
- bugfix: fixed crash when open file dialog and not selecting file and then import from mapbox (UE5)
- bugfix: fixed crash when deleting imported spline and then re-open Landscaping Tab (UE5)

## Version 4.3

- change: auto detect world partition and preselect in DTM Import Options

## Version 4.2

- change: try create default Cache Directory even when not set by user
- bugfix: removed saving zero-indexed tile for world composition after import

## Version 4.1

- bugfix: bounds center for vector import

## Version 4.0

- feature: automate Deform Landscape / Paint Layer on Vector import
- UI: grouping of vectordata import options
- feature: integrate Landscaping Mapbox plugin for easy heightdata download
- feature: quick assign Landscape Material on heightdata import
- bugfix: postition of landscape bounds
- bugfix: saving data in LandscapingInfos Actor in UE5
- change: remove `Fill the gaps` section in DTM Import Options
- change: remove `Close` button in DTM Import Options

## Version 3.0

- support for UE5 World Partition

## Version 2.10

- fixed scaling issue for vector data
- support for UE5 Preview 1

## Version 2.9

- independent Shapefile import
- plugin usable in UE5

## Version 2.8

- Export txt with scale info alongside PNG
- upsampling of DTM data

## Version 2.7

- Export PNG for reimport in UE4 and UE5
- Choose resampling algorithm of DTM files

## Version 2.6

- Scale landscape to other scale than real world scale

## Version 2.5

- Support making Blueprints from all Vectordata at once

## Version 2.4

- Support landscape below sea level (bathymetry)

## Version 2.3

- Faster reprojection of DTM files
- Show import options also after import

## Version 2.2

- Select area with map (external link)

## Version 2.1

- Heightdata import options dialog
- Fill gaps and steep edges with auxiliary files
- Always convert to UTM projection
- Popup messages with tips
- Documentation links

## Version 2.0

- LandscapingVectorInterface
- 3 new Blueprints
- Select smaller area on heightdata import
- Modify landscape height and paint layer based on splines

## Version 1.2

- Moved binaries folder

## Version 1.1

- Bugfixes
