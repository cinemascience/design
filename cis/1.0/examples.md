# Examples

## Simplest example
The simplest example is a single image with a single layer and a single channel. All other values are set to default by any application that reads this data.

|CISimage|CISLayer|CISChannel|FILE|
|-|-|-|-|
|0|0|pressure|cis0000.npz|

```
CISimage,CISLayer,CISChannel,FILE
0,0,0,pressure,cis0000.npz
```

## All data explicit for a simple layer

|CISID|CISimage|CISImageWidth|CISImageHeight|CISLayer|CISLayerOriginX|CISLayerOriginY|CISChannel|CISChannelType|FILE|
|-|-|-|-|-|-|-|-|-|-|
|0|0|512|512|0|0|0|pressure|float|cis0000.npz|

```
CISID,CISimage,CISImageWidth,CISImageHeight,CISLayer,CISLayerOriginX,CISLayerOriginY,CISChannel,CISChannelType,FILE
0,0,512,512,0,0,0,pressure,float,cis0000.npz
```
