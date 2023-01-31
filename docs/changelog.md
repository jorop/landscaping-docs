# Changelog

Changelog for the documentation see: [The Landscaping Docs on Github](https://github.com/jorop/landscaping-docs)

> Since Version 5.0 all changes only apply to UE5

## Version 7.4

- feature: write into data table from blueprint (function name: `InsertDataTableRow`)
- feature: read Geo Referencing Actor
- feature (experimental): read raster parallel - this reduces large raster imports but is a little unstable atm

## Version 7.3

- feature: update existing Landscape with heightdata from DTM files or Mapbox  
- feature: fill areas of missing data of a Landscape with data of DTM files or Mapbox  
- change: removed multiple popup dialogs when importing ASCII files without .prj file  

## Version 7.2

- feature: Landscape Splines (only UE 5.1)  
- feature: allow import of ASCII files from spain when appropriate `Custom CRS` is provided in settings  
- bugfix: engine shutdown on shapefile import  
- bugfix: bounds calculation in single level  

## Version 7.1

- feature: add collision to mesh on import  
- feature: georeferencing on nanite meshes  
- feature: scale of georeferenced actors can be changed after import  
- change: Save and replace Mesh Button moved to UI  
- change: additional imports will be resampled to first tile  

## Version 7.0

- feature: import satellite imagery as landscape material, mesh material, decal or vertex color
- feature: import dtm as mesh
- feature: integrate map selection into the `DTM Import Options` dialog
- feature: select landscape / mesh to map satellite data or vector data onto
- upgrade: gdal 3.5 / proj 7
- change: use precise scale as default

### Mapbox Version 2.0

- feature: import satellite imagery from Mapbox
- feature: import vector tiles from Mapbox

## Version 6.2

- bugfix: shapefile import of points are now working as expected with debug visualization
- upgrade: compatible with UE 5.1 Preview 1

## Version 6.1

- feature: provide shapefile attributes in `LandscapingVectorInterface`
- feature: additional setting: connect shapes (linestrings). See settings docs for further details.
- bugfix: display all shapes when selecting feature class in UI and switching back to `ALL`

## Version 6.0

- feature: create splines or blueprints from shapefile in batches  
- feature: opt out to create auxiliary actor when creating actors / blueprints  
- feature: select spline point type of generated splines on import (e.g. for buildings)  
- feature: option to align points of a spline horizontally (e.g. for buildings)  
- feature: Spline Mesh and Auxiliary Actor have an additional option `Snap to Ground` to re-align a shape with the landscape's surface  
- change: options inside `LandscapingInfos` are now sorted to topics `DTM`, `Shapefile` and `Internal`  
- change: relative scaling of landscape on import (instead of fixed value)  
- change: dropped World Composition support

## Version 5.9

- feature: smooth steps to correct blocky terrain  
- feature: set scale of actor/blueprint on import  
- change: removed upsampling (beta) - superseded by smooth steps

## Version 5.8

- feature: write out LandscapingInfos.txt - a textfile with necessary georeferencing information
- feature: faster reprojection algo is choosen automatically
- fix: vector debug preview on weightmap generation matches exactly now even when not using precise scale
- fix: fixed crash when choosing default layer after changing landscape material
- fix: fixed crash when open another level during import

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
