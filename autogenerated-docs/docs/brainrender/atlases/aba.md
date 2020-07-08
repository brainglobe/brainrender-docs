



Contents
========

* [**ABA**](#aba)
	* [**`__init__`** [#46]](#__init__-46)
	* [**`get_neurons`** [#76]](#get_neurons-76)
	* [**`get_tractography`** [#204]](#get_tractography-204)
	* [**`get_streamlines`** [#334]](#get_streamlines-334)
	* [**`get_projection_tracts_to_target`** [#387]](#get_projection_tracts_to_target-387)
	* [**`download_streamlines_for_region`** [#415]](#download_streamlines_for_region-415)
	* [**`download_streamlines_to_region`** [#440]](#download_streamlines_to_region-440)


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
## **`__init__`** [#46]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/atlases/aba.py#L46) online

```python
def __init__(self):
```  


no docstring

&nbsp;
## **`get_neurons`** [#76]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/atlases/aba.py#L76) online

```python
def get_neurons(self, neurons, color=None, display_axon=True, display_dendrites=True, alpha=1, neurite_radius=None, soma_radius=None, use_cache=True):
```  


```text
Gets rendered morphological data of neurons reconstructions
downloaded from the
mouse light project at janelia (or other sources).
accepts neurons argument as:
- file(s) with morphological data
- vedo mesh actor(s) of entire neurons reconstructions
- dictionary or list of dictionary with actors for different
neuron parts
:param neurons: str, list, dict.  file(s) with neurons data
or list of rendered neurons.
:param display_axon, display_dendrites: if set to false the
corresponding neurite is not rendered
:param color: default none.  can be:
- none: each neuron is given a random color
- color: rbg, hex etc.  if a single color is passed all
neurons will have that color
- cmap: str with name of a colormap: neurons are colored
based on their sequential order and cmap
- dict: a dictionary specifying a color for soma, dendrites
and axon actors, will be the same for all neurons
- list: a list of length = number of neurons with either a
single color for each neuron
or a dictionary of colors for each neuron
:param alpha: float in range 0,1.  neurons transparency
:param neurite_radius: float > 0 , radius of tube actor
representing neurites
:param use_cache: bool, if true a cache is used to avoid
having to crate a neuron's mesh anew, otherwise a new mesh
is created
```

&nbsp;
## **`get_tractography`** [#204]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/atlases/aba.py#L204) online

```python
def get_tractography(self, tractography, color=None, color_by='manual', others_alpha=1, verbose=True, VIP_regions=[], VIP_color=None, others_color='white', include_all_inj_regions=False, display_injection_volume=True):
```  


```text
Renders tractography data and adds it to the scene.  a
subset of tractography data can receive special treatment
using the  with vip regions argument:
if the injection site for the tractography data is in a vip
regions, this is colored differently.
:param tractography: list of dictionaries with tractography
data
:param color: color of rendered tractography data
:param color_by: str, specifies which criteria to use to
color the tractography (default value = "manual")
options:
-  manual, define color of each tract
- target_region, color by the injected region
:param others_alpha: float (default value = 1)
:param verbose: bool (default value = true)
:param vip_regions: list of brain regions with vip
treatement (default value = [])
:param vip_color: str, color to use for vip data (default
value = none)
:param others_color: str, color for not vip data (default
value = "white")
:param include_all_inj_regions: bool (default value = false)
:param display_injection_volume: float, if true a spehere is
added to display the injection coordinates and volume
(default value = true)
```

&nbsp;
## **`get_streamlines`** [#334]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/atlases/aba.py#L334) online

```python
def get_streamlines(self, sl_file, color=None, *args, **kwargs):
```  


```text
Render streamline data downloaded from
https://neuroinformatics. Nl/hbp/allen-connectivity-
viewer/streamline-downloader. Html
:param sl_file: path to json file with streamliens data [or
list of files]
:param color: either a single color or a list of colors to
color each streamline individually
:param *args:
:param **kwargs:
```

&nbsp;
## **`get_projection_tracts_to_target`** [#387]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/atlases/aba.py#L387) online

```python
def get_projection_tracts_to_target(self, p0=None, **kwargs):
```  


```text
Gets tractography data for all experiments whose projections
reach the brain region or location of iterest.
:param p0: list of 3 floats with xyz coordinates of point to
be used as seed (default value = none)
:param **kwargs:
```

&nbsp;
## **`download_streamlines_for_region`** [#415]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/atlases/aba.py#L415) online

```python
def download_streamlines_for_region(self, region, *args, **kwargs):
```  


```text
Using the allen mouse connectivity data and corresponding
api, this function finds expeirments whose injections
were targeted to the region of interest and downloads the
corresponding streamlines data.  by default, experiements
are selected for only wt mice and onl when the region was
the primary injection target.  look at "aba.
Experiments_source_search"
to see how to change this behaviour.
:param region: str with region to use for research
:param *args: arguments for aba. Experiments_source_search
:param **kwargs: arguments for aba.
Experiments_source_search
```

&nbsp;
## **`download_streamlines_to_region`** [#440]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/atlases/aba.py#L440) online

```python
def download_streamlines_to_region(self, p0, *args, mouse_line='wt', **kwargs):
```  


```text
Using the allen mouse connectivity data and corresponding
api, this function finds injection experiments
which resulted in fluorescence being found in the target
point, then downloads the streamlines data.
:param p0: list of floats with xyz coordinates
:param mouse_line: str with name of the mouse line to
use(default value = "wt")
:param *args:
:param **kwargs:
```