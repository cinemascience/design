# Examples

## CIS column keywords

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

## Simplest example
The simplest example is a single image with a single layer and a single channel. All other values are set to default by any application that reads this data.

|CISID.1.0|CISimage|CISImageWidth|CISImageHeight|CISLayer|CISChannel|FILE|
|-|-|-|-|-|-|-|
|"0"|"0"|512|512|"0"|pressure|cis0000.npz|

```
CISID.1.0,CISimage,CISImageWidth,CISImageHeight,CISLayer,CISChannel,FILE
"0","0",512,512,"0",pressure,cis0000.npz
```

## Simplest example with additional metadata
The above example can include any number of columns of additional metadata, per the Cinema database specification. For example, including timestep and camera metadata could look like this. The example includes images across several timesteps and camera positions:

|phi|theta|timestep|CISID.1.0|CISimage|CISImageWidth|CISImageHeight|CISLayer|CISChannel|FILE|
|-|-|-|-|-|-|-|-|-|-|-|-|-|-|
|0.0|0.0|0.0|"0"|"0"|512|512|"0"|pressure|cis0000.npz|
|1.0|1.0|0.0|"0"|"0"|512|512|"0"|pressure|cis0001.npz|
|0.0|0.0|1.0|"0"|"0"|512|512|"0"|pressure|cis0002.npz|
|1.0|1.0|1.0|"0"|"0"|512|512|"0"|pressure|cis0003.npz|

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
