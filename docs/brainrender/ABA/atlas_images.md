



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

--------
## line: 34 - `__init__`
  
```  
def __init__(self):
```


>  no docstring

--------
## line: 89 - `get_atlas_by_name`
  
```  
def get_atlas_by_name(self, atlas_name):
```
>Get a brain atlas in the Allen's database given it's name  
:param atlas_name: str with atlas name

--------
## line: 104 - `get_products_by_species`
  
```  
def get_products_by_species(self, species):
```
>Get all 'products' in the Allen Database for a given species  
:param species: str

--------
## line: 113 - `get_experimentsid_by_productid`
  
```  
def get_experimentsid_by_productid(self, productid, **kwargs):
```
>Get the experiment's ID that belong to the same project (product).  
:param productid: int with product ID number  
:param **kwargs: 

--------
## line: 126 - `get_experimentimages_by_expid`
  
```  
def get_experimentimages_by_expid(self, expid):
```
>Get's images that belong to an experiment  
:param expid: int with experiment name. 

--------
## line: 136 - `get_atlasimages_by_atlasid`
  
```  
def get_atlasimages_by_atlasid(self, atlasid):
```
>Get the metadata of images that belong to an atlas.   
:param atlasid: int with atlas number

--------
## line: 149 - `download_images_by_imagesid`
  
```  
def download_images_by_imagesid(self, savedir, imagesids, downsample=0, annotated=True, snames=None, atlas_svg=True):
```
>Downloads and saves images given a list of images IDs.   
:param savedir: str, folder in which to save the image  
:param imagesids: list of int with images IDs  
:param downsample: downsample factor, to reduce the image size and resolution (Default value = 0)  
:param annotated: if True the images are overlayed with annotations  (Default value = True)  
:param snames: if True the images are overlayed with the structures names (Default value = None)  
:param atlas_svg: if True fetches the images as SVG, otherwise as PNG (Default value = True)

--------
## line: 216 - `download_images_by_atlasid`
  
```  
def download_images_by_atlasid(self, savedir, atlasid, debug=False, **kwargs):
```
>Downloads all the images that belong to an altlas  
:param savedir: str, folder in which to save the images  
:param atlasid: int, ID of the atlas to use  
:param **kwargs: keyword arguments for self.download_images_by_imagesid