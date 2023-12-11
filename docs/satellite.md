# Satellite

When importing satellite data, it is possible to select the files which will be mapped onto a landscape or mesh.  

Supported filetypes: JPG2000 (*.jp2) and GeoTiff (*.tif;*.tiff) with RGB as R => 1. band, G => 2. band, B => 3. band (which is the standard).  

> With [Mapbox](mapbox?id=mapbox) the satellite imagery can be downloaded directly from mapbox with a single click.

The satellite imagery will be automatically projected and cropped to the size of the landscape or mesh.  

## Satellite Image as Decal

If set to true, a decal actor will be created and the satellite texture will be projected onto the landscape. (Default).

## Satellite Image as Vertex Color

Only available on mesh landscapes (`LandscapingProcMeshLandscape`). If set to true, the satellite image will be applied directly onto the mesh (as vertex color). When trying to import satellite imagery as vertex color on a landscape, it will fall back to decal.

## Both `Decal` and `Vertex Color` set to false

If neither decal or vertex color is checked, the satellite imagery will be created as Landscape Material on Landscapes or as as Material on Mesh Terrains.

## Mapbox Zoom Level

Zoom Level for Mapbox Satellite data import. See [Mapbox Documentation](mapbox.md). Only available with Mapbox Extension.
