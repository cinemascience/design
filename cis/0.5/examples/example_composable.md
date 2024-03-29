# Composable Image Set example

There are many ways to encode Cinema `.csv` file and image information within the **HDF5** format. Two are provided below:

1. An encoding that includes maximum information, including the `.csv` file data.
2. A minimal encoding that does not include the `.csv` file data.

## Cinema `.csv.` file

We note:

1. The `cis:path` column name is a reserved keyword noting the HDF5 path to the data within the `.cis` file.

| time | phi  | theta | isoval | isovar  | cis:path | FILE |
| ---- | ---- | ----- | ------ | ------  | ---- | -------- |
| 1.0  | 10.0 | 10.0  |  10.0  | density | /image/0000/layers/0000 | output.cis |
| 2.0  | 10.0 | 10.0  |  10.0  | density | /image/0001/layers/0000 | output.cis |

### 1. HDF5 Encoding with embedded .csv data 
```
/
  class COMPOSABLE_IMAGE_SET
  dims [1024, 768]
  version 0.5
  parametertable/
    col_names "time,phi,theta,isoval,isovar,cis:path"
    num_cols 6
    num_rows 2
    columns/
        time
        phi
        theta
        isoval
        isovar
        cis:path
  variables/
    temperature/
      type float
      min  0.0
      max  1000.0
    pressure/
      type float
      min  0.0
      max  5000.0
    procID/
      type int
      min  0
      max  1024 
  image/
    0000/
      layers/
        0000/
          channel/
            depth
            lighting
            temperature
              variable temperature
            pressure
              variable pressure
            procID
              variable procID
    0001/
      layers/
        0000/
          channel/
            depth
            lighting
            temperature
              variable temperature
            pressure
              variable pressure
            procID
              variable procID
```

### 2. HDF5 Encoding with Minimal Data

In this example, we do not encode the Cinema `.csv` file in the `.cis` file. This is a valid encoding of the data, but it relies on either introspection or an acompanying `.csv` file to allow the file to be manipulated. Note:

1. Because of defaults defined in the **CIS** specification, we can assume that the `temperature`, `pressure`, and `procID` channels represent the same data.


```
/
  class COMPOSABLE_IMAGE_SET
  dims [1024, 768]
  version 0.5
  image/
    0000/
      layers/
        0000/
          channel/
            depth
            lighting
            temperature
            pressure
            procID
    0001/
      layers/
        0000/
          channel/
            depth
            lighting
            temperature
            pressure
            procID
```
