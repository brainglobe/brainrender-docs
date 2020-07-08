



Contents
========

* [**ImageDownload**](#imagedownload)
	* [**`__init__`** [#34]](#__init__-34)
	* [**`get_atlas_by_name`** [#89]](#get_atlas_by_name-89)
	* [**`get_products_by_species`** [#104]](#get_products_by_species-104)
	* [**`get_experimentsid_by_productid`** [#113]](#get_experimentsid_by_productid-113)
	* [**`get_experimentimages_by_expid`** [#126]](#get_experimentimages_by_expid-126)
	* [**`get_atlasimages_by_atlasid`** [#136]](#get_atlasimages_by_atlasid-136)
	* [**`download_images_by_imagesid`** [#149]](#download_images_by_imagesid-149)
	* [**`download_images_by_atlasid`** [#216]](#download_images_by_atlasid-216)


&nbsp;

--------
# **ImageDownload**


```
Handles query to the Allen ImageDownloadApi and saves the data
```

&nbsp;
## **`__init__`** [#34]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/ABA/atlas_images.py#L34) online

```python
def __init__(self):
```  


no docstring

&nbsp;
## **`get_atlas_by_name`** [#89]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/ABA/atlas_images.py#L89) online

```python
def get_atlas_by_name(self, atlas_name):
```  


```text
Get a brain atlas in the allen's database given it's name
:param atlas_name: str with atlas name
```

&nbsp;
## **`get_products_by_species`** [#104]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/ABA/atlas_images.py#L104) online

```python
def get_products_by_species(self, species):
```  


```text
Get all 'products' in the allen database for a given species
:param species: str
```

&nbsp;
## **`get_experimentsid_by_productid`** [#113]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/ABA/atlas_images.py#L113) online

```python
def get_experimentsid_by_productid(self, productid, **kwargs):
```  


```text
Get the experiment's id that belong to the same project (product).
:param productid: int with product id number
:param **kwargs:
```

&nbsp;
## **`get_experimentimages_by_expid`** [#126]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/ABA/atlas_images.py#L126) online

```python
def get_experimentimages_by_expid(self, expid):
```  


```text
Get's images that belong to an experiment
:param expid: int with experiment name.
```

&nbsp;
## **`get_atlasimages_by_atlasid`** [#136]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/ABA/atlas_images.py#L136) online

```python
def get_atlasimages_by_atlasid(self, atlasid):
```  


```text
Get the metadata of images that belong to an atlas.
:param atlasid: int with atlas number
```

&nbsp;
## **`download_images_by_imagesid`** [#149]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/ABA/atlas_images.py#L149) online

```python
def download_images_by_imagesid(self, savedir, imagesids,
    downsample=0, annotated=True, snames=None, atlas_svg=True):
```  


```text
Downloads and saves images given a list of images ids.
:param savedir: str, folder in which to save the image
:param imagesids: list of int with images ids
:param downsample: downsample factor, to reduce the image size and
    resolution (default value = 0)
:param annotated: if true the images are overlayed with annotations
    (default value = true)
:param snames: if true the images are overlayed with the structures
    names (default value = none)
:param atlas_svg: if true fetches the images as svg, otherwise as png
    (default value = true)
```

&nbsp;
## **`download_images_by_atlasid`** [#216]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/ABA/atlas_images.py#L216) online

```python
def download_images_by_atlasid(self, savedir, atlasid, debug=False,
    **kwargs):
```  


```text
Downloads all the images that belong to an altlas
:param savedir: str, folder in which to save the images
:param atlasid: int, id of the atlas to use
:param **kwargs: keyword arguments for self.
    Download_images_by_imagesid
```