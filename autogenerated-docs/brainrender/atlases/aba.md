



Contents
========

* [**ABA**](#aba)
	* [**`__init__`** [#41]](#__init__-41)
	* [**`get_tractography`** [#50]](#get_tractography-50)
	* [**`get_streamlines`** [#184]](#get_streamlines-184)
	* [**`get_projection_tracts_to_target`** [#238]](#get_projection_tracts_to_target-238)
	* [**`download_streamlines_for_region`** [#271]](#download_streamlines_for_region-271)
	* [**`download_streamlines_to_region`** [#301]](#download_streamlines_to_region-301)


&nbsp;

--------
# **ABA**


```
This class augments the functionality of
BrainGlobeAtlas with methods specific to the Allen
Mouse Brain atlas and necessary to populate scenes in 
brainrender. These include stuff like fetching streamlines
and neuronal morphology data. 
```

&nbsp;
## **`__init__`** [#41]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/atlases/aba.py#L41) online

```python
def __init__(self):
```

&nbsp;  
docstring:

no docstring

&nbsp;
## **`get_tractography`** [#50]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/atlases/aba.py#L50) online

```python
def get_tractography(self, tractography, color=None,
    color_by='manual', others_alpha=1, verbose=True, VIP_regions=[],
    VIP_color=None, others_color='white', include_all_inj_regions=False,
    display_injection_volume=True):
```

&nbsp;  
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

&nbsp;
## **`get_streamlines`** [#184]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/atlases/aba.py#L184) online

```python
def get_streamlines(self, sl_file, color=None, *args, **kwargs):
```

&nbsp;  
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

&nbsp;
## **`get_projection_tracts_to_target`** [#238]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/atlases/aba.py#L238) online

```python
def get_projection_tracts_to_target(self, p0=None, **kwargs):
```

&nbsp;  
docstring:

```text
Gets tractography data for all experiments whose projections reach the
    brain region or location of iterest.

:param p0: list of 3 floats with AP-DV-ML coordinates of point to be
    used as seed (Default value = None)

:param **kwargs:

```

&nbsp;
## **`download_streamlines_for_region`** [#271]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/atlases/aba.py#L271) online

```python
def download_streamlines_for_region(self, region, *args, **kwargs):
```

&nbsp;  
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

&nbsp;
## **`download_streamlines_to_region`** [#301]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/atlases/aba.py#L301) online

```python
def download_streamlines_to_region(self, p0, *args, mouse_line='wt',
    **kwargs):
```

&nbsp;  
docstring:

```text
Using the Allen Mouse Connectivity data and corresponding API, this
    function finds injection experiments

which resulted in fluorescence being found in the target point, then
    downloads the streamlines data.

:param p0: list of floats with AP-DV-ML coordinates

:param mouse_line: str with name of the mouse line to use(Default
    value = "wt")

:param *args:

:param **kwargs:

```