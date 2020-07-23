# aba

## Contents

* [**ABA**](aba.md#aba)
  * [**`__init__`** \[\#46\]](aba.md#__init__-46)
  * [**`get_neurons`** \[\#76\]](aba.md#get_neurons-76)
  * [**`get_tractography`** \[\#204\]](aba.md#get_tractography-204)
  * [**`get_streamlines`** \[\#334\]](aba.md#get_streamlines-334)
  * [**`get_projection_tracts_to_target`** \[\#387\]](aba.md#get_projection_tracts_to_target-387)
  * [**`download_streamlines_for_region`** \[\#415\]](aba.md#download_streamlines_for_region-415)
  * [**`download_streamlines_to_region`** \[\#440\]](aba.md#download_streamlines_to_region-440)

## **ABA**

```text
This class augments the functionality of
BrainGlobeAtlas with methods specific to the Allen
Mouse Brain atlas and necessary to populate scenes in 
brainrender. These include stuff like fetching streamlines
and neuronal morphology data.
```

### **`__init__`** \[\#46\]

Check the [_**`source code`**_](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/atlases/aba.py#L46) online

```python
def __init__(self):
```

   
docstring:

no docstring

### **`get_neurons`** \[\#76\]

Check the [_**`source code`**_](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/atlases/aba.py#L76) online

```python
def get_neurons(self, neurons, color=None, display_axon=True,
    display_dendrites=True, alpha=1, neurite_radius=None,
    soma_radius=None, use_cache=True):
```

   
docstring:

```text
Gets rendered morphological data of neurons reconstructions downloaded
    from the

Mouse Light project at Janelia (or other sources).

Accepts neurons argument as:

- file(s) with morphological data

- vedo mesh actor(s) of entire neurons reconstructions

- dictionary or list of dictionary with actors for different neuron
    parts

:param neurons: str, list, dict. File(s) with neurons data or list of
    rendered neurons.

:param display_axon, display_dendrites: if set to False the
    corresponding neurite is not rendered

:param color: default None. Can be:

- None: each neuron is given a random color

- color: rbg, hex etc. If a single color is passed all neurons will
    have that color

- cmap: str with name of a colormap: neurons are colored based on
    their sequential order and cmap

- dict: a dictionary specifying a color for soma, dendrites and axon
    actors, will be the same for all neurons

- list: a list of length = number of neurons with either a single
    color for each neuron

or a dictionary of colors for each neuron

:param alpha: float in range 0,1. Neurons transparency

:param neurite_radius: float > 0 , radius of tube actor representing
    neurites

:param use_cache: bool, if True a cache is used to avoid having to
    crate a neuron's mesh anew, otherwise a new mesh is created
```

### **`get_tractography`** \[\#204\]

Check the [_**`source code`**_](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/atlases/aba.py#L204) online

```python
def get_tractography(self, tractography, color=None,
    color_by='manual', others_alpha=1, verbose=True, VIP_regions=[],
    VIP_color=None, others_color='white', include_all_inj_regions=False,
    display_injection_volume=True):
```

   
docstring:

```text
Renders tractography data and adds it to the scene. A subset of
    tractography data can receive special treatment using the  with VIP
    regions argument:

if the injection site for the tractography data is in a VIP regions,
    this is colored differently.

:param tractography: list of dictionaries with tractography data

:param color: color of rendered tractography data

:param color_by: str, specifies which criteria to use to color the
    tractography (Default value = "manual")

options:

-  manual, define color of each tract

- target_region, color by the injected region

:param others_alpha: float (Default value = 1)

:param verbose: bool (Default value = True)

:param VIP_regions: list of brain regions with VIP treatement (Default
    value = [])

:param VIP_color: str, color to use for VIP data (Default value =
    None)

:param others_color: str, color for not VIP data (Default value =
    "white")

:param include_all_inj_regions: bool (Default value = False)

:param display_injection_volume: float, if True a spehere is added to
    display the injection coordinates and volume (Default value = True)
```

### **`get_streamlines`** \[\#334\]

Check the [_**`source code`**_](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/atlases/aba.py#L334) online

```python
def get_streamlines(self, sl_file, color=None, *args, **kwargs):
```

   
docstring:

```text
Render streamline data downloaded from
    https://neuroinformatics.nl/HBP/allen-connectivity-viewer/streamline-
    downloader.html

:param sl_file: path to JSON file with streamliens data [or list of
    files]

:param color: either a single color or a list of colors to color each
    streamline individually

:param *args:

:param **kwargs:
```

### **`get_projection_tracts_to_target`** \[\#387\]

Check the [_**`source code`**_](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/atlases/aba.py#L387) online

```python
def get_projection_tracts_to_target(self, p0=None, **kwargs):
```

   
docstring:

```text
Gets tractography data for all experiments whose projections reach the
    brain region or location of iterest.

:param p0: list of 3 floats with XYZ coordinates of point to be used
    as seed (Default value = None)

:param **kwargs:
```

### **`download_streamlines_for_region`** \[\#415\]

Check the [_**`source code`**_](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/atlases/aba.py#L415) online

```python
def download_streamlines_for_region(self, region, *args, **kwargs):
```

   
docstring:

```text
Using the Allen Mouse Connectivity data and corresponding API, this
    function finds expeirments whose injections

were targeted to the region of interest and downloads the
    corresponding streamlines data. By default, experiements

are selected for only WT mice and onl when the region was the primary
    injection target. Look at "ABA.experiments_source_search"

to see how to change this behaviour.

:param region: str with region to use for research

:param *args: arguments for ABA.experiments_source_search

:param **kwargs: arguments for ABA.experiments_source_search
```

### **`download_streamlines_to_region`** \[\#440\]

Check the [_**`source code`**_](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/atlases/aba.py#L440) online

```python
def download_streamlines_to_region(self, p0, *args, mouse_line='wt',
    **kwargs):
```

   
docstring:

```text
Using the Allen Mouse Connectivity data and corresponding API, this
    function finds injection experiments

which resulted in fluorescence being found in the target point, then
    downloads the streamlines data.

:param p0: list of floats with XYZ coordinates

:param mouse_line: str with name of the mouse line to use(Default
    value = "wt")

:param *args:

:param **kwargs:
```

