# Let's get high

Making a huge tiled landscape is as easy as making a single landscape.

## Choosing input files

In order to create a tiled landscape, you can choose one or multiple files in the file selection dialog.  
Depending on the [Desired Tile Size](#desired-tile-size-max), the tiles for the landscape will be created on the fly.  
> A tiled landscape can be created from a single file or from multiple files

The controlling factor is the [Desired Tile Size](#desired-tile-size-max).  
There is only one thing to consider:
> The file size of a single GeoTiff file can be 2 GB max

## Options

The Landscaping plugin allows you to set the desired tile size and if you wish to convert to OSM projection.  

### Use OSM Projection

Wether to use OpenStreetMap/Google Maps projection or keep the original projection of the GeoTiff dataset.
If you do not know, what this means, leave it checked. It's fine. The Landscaping plugin handles everything automatically.

### Desired Tile Size (Max)

Tiles will have this width max. The unit here is kilometers (km).

## Projections

Per default, OSM projection [EPSG:3857](https://epsg.io/3857) is used. If you want to keep the original projection of your GeoTiff file, uncheck `Use OSM Projection`.

> Landscaping can handle every projection and converts it automatically

This means: you can import GeoTiff files with different projections and resolutions and they will be aligned properly. You do not have to worry about it.  

> Landscaping can handle overlapping files

This means: you can have intersecting datasets, they will be merged.

## Next Steps

Make the gray checkerd landscape colorful with [Landcover](landcover.md?id=landcover)
