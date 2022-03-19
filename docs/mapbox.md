# Mapbox

With the extension [Landscaping Mapbox](https://www.unrealengine.com/marketplace/en-US/product/landscaping-mapbox) heightmap tiles from Mapbox can easily be imported.
Therefore only the extents (bounding box) of the area must be pasted into the [DTM import Options](heights?id=import-area-optional) dialog. The heightmaps will be downloaded automatically and the Landscape / World Composition / World Partition will be created.  

## Setup and Import

1. Enable the plugin in the Plugins Tab (`Edit -> Plugins`)
2. Please make sure to provide your Mapbox API key in `Project Settings -> Plugins -> Landscaping Mapbox`.
3. Open Landscaping plugin in the Toolbar (UE4) or in the `Window` Menu (UE5)  
![Landscaping Mapbox](_media/ue4_landscaping_dtm_huge.jpg)  
4. Click on `Options` next to `DTM Import Options`
5. Click on `Show Map` on the top right corner -> a browser window with the map of the world will open
6. Make a bounding box with the rectangle tool from the left hand side
7. Copy - Paste the coordinates from the address after the # into the `Corners as bounding box` input field - the approximate area, which will be imported will appear on the top left corner. (Please do not import areas greater than a couple of thousand square kilometers, Unreal Engine needs about 20 GB RAM per 1000 km² landscape).
8. Close the `Options for DTM Import` dialog
9. Hit `Import`

> See also [DTM Import Options](heights?id=import-area-optional)

## Settings

Settings for the Plugin can be found under `Project Settings -> Plugins -> Landscaping Mapbox`.

### API key

The Api key for Mapbox. Please look it up in your mapbox account. Mapbox allows for 750000 free calls on the tiles API, which is probably more than you will ever need for the Landscaping Mapbox plugin. The Landscaping plugin caches the tiles locally, which means reimporting the landscape will not result in additional calls to Mapbox.

### Zoom

The zoom level of the heightmap tile. Best heightmaps will be delivered with zoom 15, which translates to an accuracy of ~ 2 to 4 meters.
