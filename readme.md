# Impact workshop resources for remote sensing

This is a super quick intro to get started with Python geospatial and Google Earth Engine, providing access to remote sensing data and a more general Big Earth Observation data ecosystem. Feel free to contact me for any question! 



## Getting started with Python Geospatial

- For Python virtual environments, use [Mamba](http://mamba.readthedocs.io). This might be confusing at the beginning, but make sure you:
    1. Create an environment dedicated to your geospatial analyses
    2. As much as possible, install all packages with the **conda-forge** channel
- From personal experience, I use [VSCode](https://code.visualstudio.com) to write my codes, which has a great [support](https://code.visualstudio.com/docs/languages/python) and [tutorials](https://code.visualstudio.com/docs/python/python-tutorial) for Python
- On your Python Geospatial journey, you will encounter the name of [Qiusheng Wu](https://wetlands.io), who maintains **must have** packages for analyses. You will easily recognise his packages as they all have the same documentation webpage, which provide **exercise notebooks** which are a great way to get practical examples to develop your own codes, so be sure to check them out as well as [Qiusheng Wu's amazing Youtube tutorials](https://www.youtube.com/@giswqs).
- The first one is a package that installs the most important required packages. To create an environment and install the `geospatial` package, you could simply do this (after having installed Mamba):

```
mamba create -n geo python=3.9
mamba activate geo
mamba install geopandas
mamba install geospatial -c conda-forge
```

## Some important packages

- If you are familiar with Matlab, the most direct equivalent is a package called [NumPy](https://numpy.org) (which will already be installed as part of `geospatial`). There are some useful [cheat sheets](https://mas-dse.github.io/DSE200/cheat_sheets/1_python/6_2_NumPy_for_MATLAB_users.pdf) to get the Matlab syntax into Python. 
- For geospatial analyses however, we will use mostly two types of packages that illustrate the vector/raster data format. 
  - For **vectors**, the main access to data is via [Pandas](https://pandas.pydata.org/docs/) or - most frequently - its geospatial counterpart named [GeoPandas](https://geopandas.org/en/stable/docs.html). Most of us are familiar with shapefiles, and these packages provide data access in the shape as the attribute table. 
  - For **rasters**, the main access to data is [Xarray](https://docs.xarray.dev/en/stable/) with the geospatial bit provided by [rioxarray](https://corteva.github.io/rioxarray/stable/). The shape of the data is a Netcdf-type of file, i.e., multidimensional, labelled gridded data. 
- Visualising data is also probably a good idea. [Matplotlib](https://matplotlib.org) is the main plotting backend for Python, but let's highlight two options for plotting maps:
  - [Cartopy](https://scitools.org.uk/cartopy/docs/latest/) is a good option to prepare publication-ready maps 
  - [Leafmap](https://leafmap.org) is a great option to plot interactive maps and, guess what, it is fully integrated with `GeoPandas` and `Xarray`! 

## Google Earth Engine 

- [Google Earth Engine](https://earthengine.google.com) (or GEE) is a geospatial cloud-computing platform that provides access to multiple petabytes of data as well as a computing power to analyse complex processes at the global scale. There are two main data catalogues that will allow you to discover the wealth of accessible data:
  - The official [data catalogue](https://developers.google.com/earth-engine/datasets)
  - The community-maintained [awesome-gee-community-catalog](https://gee-community-catalog.org)
- Since last year, Google has been greatly developing the Python API to GEE. However, the [official documentation](https://developers.google.com/earth-engine/guides) is often illustrated using the JavaScript API. Thank whichever god you believe in, Qiusheng Wu and others have our backs covered with great community-developed packages.
  - [geemap](https://geemap.org): Mapping and quick routines, check the example notebooks to illustrate what is possible 
  - [eeMont](https://eemont.readthedocs.io/en/latest/): Facilitates some computations