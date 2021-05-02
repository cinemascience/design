# Examples

## Simplest example
The simplest example is a single image with a single layer and a single channel. All other values are set to default by any application that reads this data.

|phi|theta|CISID|CISimage|CISlayer|CISchannel|FILE
|-|-|-|-|-|-|-|
|0|0|0|0|pressure|cis0000.npz|

```
phi,theta,CISID,CISimage,CISlayer,CISchannel,FILE
0,0,0,0,0,pressure,cis0000.npz
```

## A set of channels for a layer
|phi|theta|CISID|CISimage|CISlayer|CISchannel|FILE
|-|-|-|-|-|-|-|
|0|0|0|0|0|pressure|cis0000.npz|
|0|0|0|0|0|procID|cis0000.npz|
|0|0|0|0|0|temperature|cis0000.npz|

```
phi,theta,CISID,CISimage,CISlayer,CISchannel,FILE
0,0,0,0,0,pressure,cis0000.npz
0,0,0,0,0,procID,cis0000.npz
0,0,0,0,0,temperature,cis0000.npz
```

## All data explicit for a simple layer

|phi|theta|CISID|CISimage|CISimageSize|CISlayer|CISchannel|FILE
|-|-|-|-|-|-|-|
|0|0|0|0|pressure|cis0000.npz|

```
phi,theta,CISID,CISimage,CISlayer,CISchannel,FILE
0,0,0,0,0,pressure,cis0000.npz
```
