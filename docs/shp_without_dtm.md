# Vectordata Import without prior DTM import

The normal workflow is to import a Landscape (DTM or from Mapbox) first, and then import the shapefiles accordingly.

It is however possible, to import the shapefiles for an already existing landscape.  

Please note, that the opposite way does not work! It is not possible to import a shapefile and afterwards a DTM!  

## Steps to import a Vectordata

If no Landscape is found in the scene, a dummy landscape with no extents will be created after click on `Select` in the `Import Roads, Railtracks, Rivers, etc.` section, then a popup `Anchor for Landscape` will appear.  
If a Landscape was not imported through the Landscaping plugin, the same popup will appear prior to selecting a Vectordata file:  
![Shapefile Anchor](_media/ue4_landscaping_anchor.jpg)  
a. `Apply` will look for a Geo Referencing System in the Scene and set the CRS (Coordinate Reference System) accordingly.  
b. `Autodetect` tries to set the CRS (Coordinate Reference System) and anchor from the Shapefile. This will not match any pre-existing landscapes, but with the LandscapingInfos Actor in the World Outliner, the Anchor can be moved to match the shapes with the Landscape - see [Enable Vector Debugging](landscapinginfos.md?id=draw-vector-data-debug).  

The shapes can be adjusted using `XYOffset` and `Vector Data Scale` properties in the `LandscapingInfos` Actors's details panel.  
