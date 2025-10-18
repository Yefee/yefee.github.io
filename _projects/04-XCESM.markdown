---
layout: page
title: xCESM
description: Xcesm provides an easy-to-use plugin in xarray to diagnose CESM output. 
img: https://github.com/Yefee/yefee_backup.github.io/blob/master/2017/12/25/XCESM/cover.gif?raw=true
importance: 2
category: Open-Science
---



# Features
Xcesm is still in developing, right now it has the following features:
* Quick plot on global map (quickmap)
* Regrid pop output to linear grids (regrid, nearest interpolation)
* Compute global mean (gbmean, gbmeanpop)
* Diagnose AMOC, PRECP, d18O(only support for iCESM), Heat transport etc.
* Truncate ocean as several main basins (ocean_region)
* and many more!

More feature will be added in the future.

# How to install
### via git
```
git clone https://github.com/Yefee/xcesm.git
cd xcesm
python setup.py install
```

# How to use
### regrid
```
import xarray as xr
import xcesm
ds = xr.open_dataset('/examples/data/salt.nc')
# defalut to 1x1 degree
salt_rgd = ds.SALT.utils.regrid()

print(ds.SALT.shape)
(384, 320)

print(salt_rgd.shape)
(181, 361)
```

### quick plot
```
salt_rgd.utils.quickmap()
```
![salt_distribution](https://github.com/Yefee/xcesm/blob/master/xcesm/examples/fig/salt.png)


