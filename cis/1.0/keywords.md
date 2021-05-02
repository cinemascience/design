# Keywords

The following are reserved keywords that implement the CIS extension metadata:

|Keyword| Required | Type | Definition |
|-|-|-|-|
|CISID              |X|string|ID of the image, and version number of the CIS spec|
|CISIDVariable      | |string|key, value set of metadata about a variable|
|CISOrigin          | |string|One of "UL, UR, LL, LR". Default is UL|
|CISImage           |X|string|ID of the image. Any unique string on the path CISID|
|CISImageFlags      | |string|List of image flags|
|CISImageWidth      |X|int   |Integer, number of pixels in width|
|CISImageHeight     |X|int   |Integer, number of pixels in height|
|CISLayer           |X|string|ID of the layer. Any unique string on the path CISID/CISImage| 
|CISLayerOffsetX    | |int   |Integer, number of pixels to offset layer origin|
|CISLayerOffsetY    | |int   |Integer, number of pixels to offset layer origin|
|CISLayerWidth      | |int   |Integer, number of pixels in width|
|CISLayerHeight     | |int   |Integer, number of pixels in height|
|CISChannel         |X|string|ID of the channel. Any unique string on the path CISID/CISImage/CISLayer| 
|CISChannelVariable | |string|Variable for the channel, if different from the Channel ID|
|CISChannelType     | |string|Type of data in the channel. One of string, int, float|


### CISImageFlags

- IMAGES_INDEPENDENT images DO NOT have the same set of layers and channels. 
    Default, if this flag is not included, is that all images 
    have the same layers, and all layers have the same channels.
