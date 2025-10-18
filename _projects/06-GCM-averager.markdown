---
layout: page
title: GCMAverager
description: GCMAverager is a package to post-process raw climate model output.
img: https://github.com/Yefee/yefee_backup.github.io/blob/master/2017/12/25/GCM-Averager/cover.jpg?raw=true
importance: 4
category: Open-Science
---

# About GCMAverager

GCMAverager stands as a lightweight post-processing package specially crafted to handle vast quantities of General Circulation Model (GCM) outputs with the aid of parallel computing. Originally designed for processing extensive data from the Community Earth System Model (CESM), which generates hundreds of terabytes of data, GCMAverager efficiently carries out its tasks.

Unlike the inadequately maintained and user-unfriendly alternatives developed by NCAR, namely pyAverager and pyReshaper, GCMAverager offers a powerful and easy-to-use solution for post-processing GCM outputs.

This xarray-based project currently excels in the following capabilities:
* Extracting variables from time slice history files and converting them into time series files.
* Computing annual (decadal) and seasonal means for model outputs from either time slice or time series files.


# Installation
### via github
```
git clone https://github.com/Yefee/gcmaverager.git
cd gcmaverager
python setup.py install
```

### via pip
```
pip install gcmaverager
```

# Get started
GCMAverager supports several kinds of average method:
* ANN (annual mean)
* MAM (March-April-May, annual mean) 
* JJA (June-July-August, annual mean) 
* SON (September-October-November, annual mean) 
* DJF (December-January-February, annual mean) 
* decadal-ANN (decadal annual mean)
* decadal-MAM (March-April-May, decadal annual mean) 
* decadal-SON (June-July-August, decadal annual mean) 
* decadal-JJA (September-October-November, decadal annual mean) 
* decadal-DJF (December-January-February, decadal annual mean) 
* TS (extract time series file from original GCM outputs)

### Extract time series file from time slice files
This feature only suppports Py 3.x.

```
    import gcmaverager as ga
    import xarray as xr

    rootDir = '/Volumes/Chengfei_Data_Center/iTrace/test/'
    tarDir = '/Volumes/Chengfei_Data_Center/iTrace/output/'
    prefix = 'test'
    suffix = '0001-0999'
    method = ['TS']

    # get file list and create an xarray object
    fl = ga.getFilelist(rootDir)
    ds = xr.open_mfdataset(fl, decode_times=False, atuoclose=True)

    # derive time dependent variables
    varList = ds.variables.keys()
    varList = [v for v in varList if "time" in ds[
        v].dims and len(ds[v].dims) > 2]

    # feed it to GAMAverager
    fl = [ds[var] for var in varList]
    ga.averager(fl, tarDir, prefix, suffix,  method)
```

The outputs are in tarDir, which has pattern prefix+variable+suffix+'.nc'(e.g. test.TEMP.0001-0999.nc)


### Compute average from time slice files
This feature only suppports Py 3.x.

```

    import gcmaverager as ga
    import xarray as xr

    rootDir = '/Volumes/Chengfei_Data_Center/iTrace/test/'
    tarDir = '/Volumes/Chengfei_Data_Center/iTrace/output/'
    prefix = 'test'
    suffix = '0001-0999'
    method = ['ANN', 'decadal-ANN']

    # get file list and create an xarray object
    fl = ga.getFilelist(rootDir)
    ds = xr.open_mfdataset(fl, decode_times=False, atuoclose=True)

    # derive time dependent variables
    varList = ds.variables.keys()
    varList = [v for v in varList if "time" in ds[
        v].dims and len(ds[v].dims) > 2]

    # feed it to GAMAverager
    fl = [ds[var] for var in varList]
    ga.averager(fl, tarDir, prefix, suffix,  method)

```
The outputs are in tarDir, which has pattern prefix+variable+suffix+'ANN.nc'(e.g. test.TEMP.0001-0999.ANN.nc)


### Compute average from time series files

```

    import gcmaverager as ga

    rootDir = '/Volumes/Chengfei_Data_Center/iTrace/test/'
    tarDir = '/Volumes/Chengfei_Data_Center/iTrace/output/'
    prefix = 'test'
    suffix = '0001-0999'
    method = ['ANN', 'decadal-ANN']

    # get file list and create an xarray object
    fl = ga.getFilelist(rootDir)

    # feed it to GAMAverager
    ga.averager(fl, tarDir, prefix, suffix,  method)

```
