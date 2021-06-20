# Troubleshooting

## Unreal Engine Editor won't start

If you see this message:  

![UE4 Message](_media/ue4_message.jpg)

Please copy the files and folders from  
`{Engine Plugin Folder}/Marketplace/Landscaping/Source/ThirdParty/Redist/Win64/`  
to  
`{Engine Plugin Folder}/Marketplace/Landscaping/Binaries/Win64/`

The `Engine Plugin Folder` can be found where the Unreal Engine Editor is installed on your system, e.g.  
`C:/Program Files/Epic Games/UE_4.26/Engine/Plugins`

## Changing Levels

When changing levels, the plugin may not detect the new World which is neccessary to save the metadata. Please close the `Landscaping Tab` and open it again. Thank you.

## Edges on the outmost border

Due to the transformation of the input data, on areas, where no data is found the height is set to 0. Therefore, steep edges on outmost borders of the Landscape or World Composition occur. Normally, this is not a problem and does not have any perfomance impacts.  
If this is a problem there are 2 options to solve this:

- The steep edges can easily be fixed within the native Unreal Engine Landscape Mode Sculpting Tools
- Use one of the options in the [DTM Import Options](heights.md?id=options) dialog

## Missing Tiles

When importing a Tiled Landscape you will maybe notice, that there are a couple of the enumerated Tiles missing. __Good news__: they are not really missing. They just did have no data and where therefore not imported at all. If you need flat tiles with all heights set to 0, you can easily add them within World Composition.

## Crashes

If the Unreal Editor crashes on import, it may due to corrupted input data. Please send the data to `support@ludicdrive.com` to verify if it is a bug in the plugin or if the input data is to blame. Thank you.
