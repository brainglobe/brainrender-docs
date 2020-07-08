



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

&nbsp;  
docstring:

no docstring

&nbsp;
## **`get_atlas_by_name`** [#89]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/ABA/atlas_images.py#L89) online

```python
def get_atlas_by_name(self, atlas_name):
```

&nbsp;  
docstring:<pre style="background-color:rgba(0, 0, 0, .2);                     border-radius:12px;                     padding:12px 24px;                     box-shadow: 1px 1px 1px rgba(0, 0, 0, .1)">Get a brain atlas in the Allen's database given it's name

:param atlas_name: str with atlas name
</pre>

&nbsp;
## **`get_products_by_species`** [#104]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/ABA/atlas_images.py#L104) online

```python
def get_products_by_species(self, species):
```

&nbsp;  
docstring:<pre style="background-color:rgba(0, 0, 0, .2);                     border-radius:12px;                     padding:12px 24px;                     box-shadow: 1px 1px 1px rgba(0, 0, 0, .1)">Get all 'products' in the Allen Database for a given species

:param species: str
</pre>

&nbsp;
## **`get_experimentsid_by_productid`** [#113]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/ABA/atlas_images.py#L113) online

```python
def get_experimentsid_by_productid(self, productid, **kwargs):
```

&nbsp;  
docstring:<pre style="background-color:rgba(0, 0, 0, .2);                     border-radius:12px;                     padding:12px 24px;                     box-shadow: 1px 1px 1px rgba(0, 0, 0, .1)">Get the experiment's ID that belong to the same project (product).

:param productid: int with product ID number

:param **kwargs:
</pre>

&nbsp;
## **`get_experimentimages_by_expid`** [#126]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/ABA/atlas_images.py#L126) online

```python
def get_experimentimages_by_expid(self, expid):
```

&nbsp;  
docstring:<pre style="background-color:rgba(0, 0, 0, .2);                     border-radius:12px;                     padding:12px 24px;                     box-shadow: 1px 1px 1px rgba(0, 0, 0, .1)">Get's images that belong to an experiment

:param expid: int with experiment name.
</pre>

&nbsp;
## **`get_atlasimages_by_atlasid`** [#136]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/ABA/atlas_images.py#L136) online

```python
def get_atlasimages_by_atlasid(self, atlasid):
```

&nbsp;  
docstring:<pre style="background-color:rgba(0, 0, 0, .2);                     border-radius:12px;                     padding:12px 24px;                     box-shadow: 1px 1px 1px rgba(0, 0, 0, .1)">Get the metadata of images that belong to an atlas.

:param atlasid: int with atlas number
</pre>

&nbsp;
## **`download_images_by_imagesid`** [#149]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/ABA/atlas_images.py#L149) online

```python
def download_images_by_imagesid(self, savedir, imagesids,
    downsample=0, annotated=True, snames=None, atlas_svg=True):
```

&nbsp;  
docstring:<pre style="background-color:rgba(0, 0, 0, .2);                     border-radius:12px;                     padding:12px 24px;                     box-shadow: 1px 1px 1px rgba(0, 0, 0, .1)">Downloads and saves images given a list of images IDs.

:param savedir: str, folder in which to save the image

:param imagesids: list of int with images IDs

:param downsample: downsample factor, to reduce the image size and
    resolution (Default value = 0)

:param annotated: if True the images are overlayed with annotations
    (Default value = True)

:param snames: if True the images are overlayed with the structures
    names (Default value = None)

:param atlas_svg: if True fetches the images as SVG, otherwise as PNG
    (Default value = True)
</pre>

&nbsp;
## **`download_images_by_atlasid`** [#216]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/ABA/atlas_images.py#L216) online

```python
def download_images_by_atlasid(self, savedir, atlasid, debug=False,
    **kwargs):
```

&nbsp;  
docstring:<pre style="background-color:rgba(0, 0, 0, .2);                     border-radius:12px;                     padding:12px 24px;                     box-shadow: 1px 1px 1px rgba(0, 0, 0, .1)">Downloads all the images that belong to an altlas

:param savedir: str, folder in which to save the images

:param atlasid: int, ID of the atlas to use

:param **kwargs: keyword arguments for
    self.download_images_by_imagesid
</pre>