# Satellite

When importing satellite data, it is possible to select the files which will be mapped onto a landscape or mesh.  

Supported filetypes: JPG2000 (*.jp2) and GeoTiff (*.tif;*.tiff) with RGB as R => 1. band, G => 2. band, B => 3. band (which is the standard).  

> With [Mapbox](mapbox?id=mapbox) the satellite imagery can be downloaded directly from mapbox with a single click.

The satellite imagery will be automatically projected and cropped to the size of the landscape or mesh.  

## Import as Decal

A decal actor will be created and the satellite texture will be projected onto the landscape.

## Import as Vertex Color

Only available on mesh landscapes (`LandscapingProcMeshLandscape`). The satellite image will be applied directly onto the mesh (as vertex color). When trying to import satellite imagery as vertex color on a landscape, it will fall back to decal.

## Default

If neither decal or vertex color is checked, the satellite imagery will be safed as 8k texture and a material will be created, the texture assigned and the material will be assiged to the Landscape (as Landscape Material) or to the Mesh (as Material).
