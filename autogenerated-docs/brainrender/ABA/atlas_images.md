



Contents
========

* [**ImageDownload**](#imagedownload)
	* [**`__init__`** [#44]](#__init__-44)
	* [**`get_atlas_by_name`** [#95]](#get_atlas_by_name-95)
	* [**`get_atlas_dataset_id_by_name`** [#110]](#get_atlas_dataset_id_by_name-110)
	* [**`get_products_by_species`** [#114]](#get_products_by_species-114)
	* [**`get_experimentsid_by_productid`** [#123]](#get_experimentsid_by_productid-123)
	* [**`get_experimentimages_by_expid`** [#136]](#get_experimentimages_by_expid-136)
	* [**`get_atlasimages_by_atlasid`** [#146]](#get_atlasimages_by_atlasid-146)
	* [**`download_images_by_imagesid`** [#159]](#download_images_by_imagesid-159)
	* [**`download_images_by_atlasid`** [#223]](#download_images_by_atlasid-223)


&nbsp;

--------
# **ImageDownload**


```
Handles query to the Allen ImageDownloadApi and saves the data
```

&nbsp;
## **`__init__`** [#44]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/ABA/atlas_images.py#L44) online

```python
def __init__(self):
```

&nbsp;  
docstring:

no docstring

&nbsp;
## **`get_atlas_by_name`** [#95]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/ABA/atlas_images.py#L95) online

```python
def get_atlas_by_name(self, atlas_name):
```

&nbsp;  
docstring:

```text
Get a brain atlas in the Allen's database given it's name

:param atlas_name: str with atlas name

```

&nbsp;
## **`get_atlas_dataset_id_by_name`** [#110]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/ABA/atlas_images.py#L110) online

```python
def get_atlas_dataset_id_by_name(self, atlas_name):
```

&nbsp;  
docstring:

no docstring

&nbsp;
## **`get_products_by_species`** [#114]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/ABA/atlas_images.py#L114) online

```python
def get_products_by_species(self, species):
```

&nbsp;  
docstring:

```text
Get all 'products' in the Allen Database for a given species

:param species: str

```

&nbsp;
## **`get_experimentsid_by_productid`** [#123]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/ABA/atlas_images.py#L123) online

```python
def get_experimentsid_by_productid(self, productid, **kwargs):
```

&nbsp;  
docstring:

```text
Get the experiment's ID that belong to the same project (product).

:param productid: int with product ID number

:param **kwargs:

```

&nbsp;
## **`get_experimentimages_by_expid`** [#136]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/ABA/atlas_images.py#L136) online

```python
def get_experimentimages_by_expid(self, expid):
```

&nbsp;  
docstring:

```text
Get's images that belong to an experiment

:param expid: int with experiment name.

```

&nbsp;
## **`get_atlasimages_by_atlasid`** [#146]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/ABA/atlas_images.py#L146) online

```python
def get_atlasimages_by_atlasid(self, atlasid):
```

&nbsp;  
docstring:

```text
Get the metadata of images that belong to an atlas.

:param atlasid: int with atlas number

```

&nbsp;
## **`download_images_by_imagesid`** [#159]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/ABA/atlas_images.py#L159) online

```python
def download_images_by_imagesid(self, savedir, imagesids,
    downsample=0, annotated=True, snames=None, atlas_svg=True):
```

&nbsp;  
docstring:

```text
Downloads and saves images given a list of images IDs.

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

```

&nbsp;
## **`download_images_by_atlasid`** [#223]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/ABA/atlas_images.py#L223) online

```python
def download_images_by_atlasid(self, savedir, atlasid, debug=False,
    **kwargs):
```

&nbsp;  
docstring:

```text
Downloads all the images that belong to an altlas

:param savedir: str, folder in which to save the images

:param atlasid: int, ID of the atlas to use

:param **kwargs: keyword arguments for
    self.download_images_by_imagesid

```