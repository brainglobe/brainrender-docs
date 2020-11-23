# atlas\_images

## Contents

* [**ImageDownload**](atlas_images.md#imagedownload)
  * [**`__init__`** \[\#34\]](atlas_images.md#__init__-34)
  * [**`get_atlas_by_name`** \[\#89\]](atlas_images.md#get_atlas_by_name-89)
  * [**`get_products_by_species`** \[\#104\]](atlas_images.md#get_products_by_species-104)
  * [**`get_experimentsid_by_productid`** \[\#113\]](atlas_images.md#get_experimentsid_by_productid-113)
  * [**`get_experimentimages_by_expid`** \[\#126\]](atlas_images.md#get_experimentimages_by_expid-126)
  * [**`get_atlasimages_by_atlasid`** \[\#136\]](atlas_images.md#get_atlasimages_by_atlasid-136)
  * [**`download_images_by_imagesid`** \[\#149\]](atlas_images.md#download_images_by_imagesid-149)
  * [**`download_images_by_atlasid`** \[\#216\]](atlas_images.md#download_images_by_atlasid-216)

## **ImageDownload**

```text
Handles query to the Allen ImageDownloadApi and saves the data
```

### **`__init__`** \[\#34\]

Check the [_**`source code`**_](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/ABA/atlas_images.py#L34) online

```python
def __init__(self):
```

   
docstring:

no docstring

### **`get_atlas_by_name`** \[\#89\]

Check the [_**`source code`**_](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/ABA/atlas_images.py#L89) online

```python
def get_atlas_by_name(self, atlas_name):
```

   
docstring:

```text
Get a brain atlas in the Allen's database given it's name

:param atlas_name: str with atlas name
```

### **`get_products_by_species`** \[\#104\]

Check the [_**`source code`**_](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/ABA/atlas_images.py#L104) online

```python
def get_products_by_species(self, species):
```

   
docstring:

```text
Get all 'products' in the Allen Database for a given species

:param species: str
```

### **`get_experimentsid_by_productid`** \[\#113\]

Check the [_**`source code`**_](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/ABA/atlas_images.py#L113) online

```python
def get_experimentsid_by_productid(self, productid, **kwargs):
```

   
docstring:

```text
Get the experiment's ID that belong to the same project (product).

:param productid: int with product ID number

:param **kwargs:
```

### **`get_experimentimages_by_expid`** \[\#126\]

Check the [_**`source code`**_](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/ABA/atlas_images.py#L126) online

```python
def get_experimentimages_by_expid(self, expid):
```

   
docstring:

```text
Get's images that belong to an experiment

:param expid: int with experiment name.
```

### **`get_atlasimages_by_atlasid`** \[\#136\]

Check the [_**`source code`**_](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/ABA/atlas_images.py#L136) online

```python
def get_atlasimages_by_atlasid(self, atlasid):
```

   
docstring:

```text
Get the metadata of images that belong to an atlas.

:param atlasid: int with atlas number
```

### **`download_images_by_imagesid`** \[\#149\]

Check the [_**`source code`**_](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/ABA/atlas_images.py#L149) online

```python
def download_images_by_imagesid(self, savedir, imagesids,
    downsample=0, annotated=True, snames=None, atlas_svg=True):
```

   
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

### **`download_images_by_atlasid`** \[\#216\]

Check the [_**`source code`**_](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/ABA/atlas_images.py#L216) online

```python
def download_images_by_atlasid(self, savedir, atlasid, debug=False,
    **kwargs):
```

   
docstring:

```text
Downloads all the images that belong to an altlas

:param savedir: str, folder in which to save the images

:param atlasid: int, ID of the atlas to use

:param **kwargs: keyword arguments for
    self.download_images_by_imagesid
```

