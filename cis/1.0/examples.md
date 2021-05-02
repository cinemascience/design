# Examples

## CIS column keywords

|Keyword| Required | Definition |
|-|-|-|
|CISID              |X|ID of the image, and version number of the CIS spec|
|CISIDVariable      | |key, value set of metadata about a variable|
|CISOrigin          | |One of "UL, UR, LL, LR". Default is UL|
|CISImage           |X|ID of the image. Any unique string on the path CISID/CISImage|
|CISImageFlags      | |List of image flags|
|CISImageWidth      |X|Integer, number of pixels in width|
|CISImageHeight     |X|Integer, number of pixels in height|
|CISLayer           |X|ID of the layer. Any unique string on the path CISIS/CISImage| 
|CISLayerOffsetX    | |Integer, number of pixels to offset layer origin|
|CISLayerOffsetY    | |Integer, number of pixels to offset layer origin|
|CISLayerWidth      | |Integer, number of pixels in width|
|CISLayerHeight     | |Integer, number of pixels in height|
|CISChannel         |X|ID of the channel. Any unique string on the path CISID/CISImage/CISChannel| 
|CISChannelVariable | |Variable for the channel, if different from the Channel ID|
|CISChannelType     | |ID of the image, and version number of the CIS spec|

## Simplest example
The simplest example is a single image with a single layer and a single channel. All other values are set to default by any application that reads this data.

|CISID.1.0|CISimage|CISImageWidth|CISImageHeight|CISLayer|CISChannel|FILE|
|-|-|-|-|-|-|-|
|"0"|"0"|512|512|"0"|pressure|cis0000.npz|

```
CISID.1.0,CISimage,CISImageWidth,CISImageHeight,CISLayer,CISChannel,FILE
"0","0",512,512,"0",pressure,cis0000.npz
```

## Example with some data explicit 
This example provides values for the `CISImageWidth`, and `CISImageHeight` values.

|CISID.1.0|CISImage|CISImageOrigin|CISImageWidth|CISImageHeight|CISLayer|CISChannel|CISChannelType|FILE|
|-|-|-|-|-|-|-|-|-|
|"0"|"0"|UL|512|512|"0"|pressure|float|cis0000.npz|

```
CISID.1.0,CISImage,CISImageWidth,CISImageHeight,CISLayer,CISChannel,CISChanne,FlILE
"0","0",UL,512,512,"0",pressure,float,cis0000.npz
```
