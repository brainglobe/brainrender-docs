



Contents
========

* [**ImageDownload**](#imagedownload)
* [line: 34 - `__init__`](#line-34---__init__)
* [line: 89 - `get_atlas_by_name`](#line-89---get_atlas_by_name)
* [line: 104 - `get_products_by_species`](#line-104---get_products_by_species)
* [line: 113 - `get_experimentsid_by_productid`](#line-113---get_experimentsid_by_productid)
* [line: 126 - `get_experimentimages_by_expid`](#line-126---get_experimentimages_by_expid)
* [line: 136 - `get_atlasimages_by_atlasid`](#line-136---get_atlasimages_by_atlasid)
* [line: 149 - `download_images_by_imagesid`](#line-149---download_images_by_imagesid)
* [line: 216 - `download_images_by_atlasid`](#line-216---download_images_by_atlasid)


&nbsp;

--------

--------
# **ImageDownload**


```
Handles query to the Allen ImageDownloadApi and saves the data
```

&nbsp;

--------
# line: 34 - `__init__`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/ABA/atlas_images.py#L34) online
#### function definition


```python
def __init__(self):
```
##### docstring
  


```python

"""
 no docstring 
"""
```

&nbsp;

--------
# line: 89 - `get_atlas_by_name`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/ABA/atlas_images.py#L89) online
#### function definition


```python
def get_atlas_by_name(self, atlas_name):
```
##### docstring
  


```python

"""
    Get a brain atlas in the Allen's database given it's name
    
    :param atlas_name: str with atlas name
"""
```

&nbsp;

--------
# line: 104 - `get_products_by_species`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/ABA/atlas_images.py#L104) online
#### function definition


```python
def get_products_by_species(self, species):
```
##### docstring
  


```python

"""
    Get all 'products' in the Allen Database for a given species
    
    :param species: str
"""
```

&nbsp;

--------
# line: 113 - `get_experimentsid_by_productid`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/ABA/atlas_images.py#L113) online
#### function definition


```python
def get_experimentsid_by_productid(self, productid, **kwargs):
```
##### docstring
  


```python

"""
    Get the experiment's ID that belong to the same project (product).
    
    :param productid: int with product ID number
    :param **kwargs: 
"""
```

&nbsp;

--------
# line: 126 - `get_experimentimages_by_expid`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/ABA/atlas_images.py#L126) online
#### function definition


```python
def get_experimentimages_by_expid(self, expid):
```
##### docstring
  


```python

"""
    Get's images that belong to an experiment
    
    :param expid: int with experiment name. 
"""
```

&nbsp;

--------
# line: 136 - `get_atlasimages_by_atlasid`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/ABA/atlas_images.py#L136) online
#### function definition


```python
def get_atlasimages_by_atlasid(self, atlasid):
```
##### docstring
  


```python

"""
    Get the metadata of images that belong to an atlas. 
    
    :param atlasid: int with atlas number
"""
```

&nbsp;

--------
# line: 149 - `download_images_by_imagesid`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/ABA/atlas_images.py#L149) online
#### function definition


```python
def download_images_by_imagesid(self, savedir, imagesids, downsample=0, annotated=True, snames=None, atlas_svg=True):
```
##### docstring
  


```python

"""
    Downloads and saves images given a list of images IDs. 
    
    
    :param savedir: str, folder in which to save the image
    :param imagesids: list of int with images IDs
    :param downsample: downsample factor, to reduce the image size and resolution (Default value = 0)
    :param annotated: if True the images are overlayed with annotations  (Default value = True)
    :param snames: if True the images are overlayed with the structures names (Default value = None)
    :param atlas_svg: if True fetches the images as SVG, otherwise as PNG (Default value = True)
"""
```

&nbsp;

--------
# line: 216 - `download_images_by_atlasid`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/ABA/atlas_images.py#L216) online
#### function definition


```python
def download_images_by_atlasid(self, savedir, atlasid, debug=False, **kwargs):
```
##### docstring
  


```python

"""
    Downloads all the images that belong to an altlas
    
    :param savedir: str, folder in which to save the images
    :param atlasid: int, ID of the atlas to use
    :param **kwargs: keyword arguments for self.download_images_by_imagesid
"""
```