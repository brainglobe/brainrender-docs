



Contents
========

* [**ABA**](#aba)
	* [line: 46 - `__init__`](#line-46---__init__)
	* [line: 76 - `get_neurons`](#line-76---get_neurons)
	* [line: 204 - `get_tractography`](#line-204---get_tractography)
	* [line: 334 - `get_streamlines`](#line-334---get_streamlines)
	* [line: 387 - `get_projection_tracts_to_target`](#line-387---get_projection_tracts_to_target)
	* [line: 415 - `download_streamlines_for_region`](#line-415---download_streamlines_for_region)
	* [line: 440 - `download_streamlines_to_region`](#line-440---download_streamlines_to_region)


&nbsp;

--------

--------
# **ABA**
  
```  
This class augments the functionality of
BrainGlobeAtlas with methods specific to the Allen
Mouse Brain atlas and necessary to populate scenes in 
brainrender. These include stuff like fetching streamlines
and neuronal morphology data.   
```

--------
## line: 46 - `__init__`
  
```  
def __init__(self):
```


>  no docstring

--------
## line: 76 - `get_neurons`
  
```  
def get_neurons(self, neurons, color=None, display_axon=True, display_dendrites=True, alpha=1, neurite_radius=None, soma_radius=None, use_cache=True):
```
>Gets rendered morphological data of neurons reconstructions downloaded from theMouse Light project at Janelia (or other sources). Accepts neurons argument as:    - file(s) with morphological data    - vedo mesh actor(s) of entire neurons reconstructions    - dictionary or list of dictionary with actors for different neuron parts  
:param neurons: str, list, dict. File(s) with neurons data or list of rendered neurons.  
:param display_axon, display_dendrites: if set to False the corresponding neurite is not rendered  
:param color: default None. Can be:        - None: each neuron is given a random color        - color: rbg, hex etc. If a single color is passed all neurons will have that color        - cmap: str with name of a colormap: neurons are colored based on their sequential order and cmap        - dict: a dictionary specifying a color for soma, dendrites and axon actors, will be the same for all neurons        - list: a list of length = number of neurons with either a single color for each neuron                or a dictionary of colors for each neuron  
:param alpha: float in range 0,1. Neurons transparency  
:param neurite_radius: float > 0 , radius of tube actor representing neurites  
:param use_cache: bool, if True a cache is used to avoid having to crate a neuron's mesh anew, otherwise a new mesh is created

--------
## line: 204 - `get_tractography`
  
```  
def get_tractography(self, tractography, color=None, color_by='manual', others_alpha=1, verbose=True, VIP_regions=[], VIP_color=None, others_color='white', include_all_inj_regions=False, display_injection_volume=True):
```
>Renders tractography data and adds it to the scene. A subset of tractography data can receive special treatment using the  with VIP regions argument:if the injection site for the tractography data is in a VIP regions, this is colored differently.  
:param tractography: list of dictionaries with tractography data  
:param color: color of rendered tractography data  
:param color_by: str, specifies which criteria to use to color the tractography (Default value = "manual")                options:                    -  manual, define color of each tract                    - target_region, color by the injected region  
:param others_alpha: float (Default value = 1)  
:param verbose: bool (Default value = True)  
:param VIP_regions: list of brain regions with VIP treatement (Default value = [])  
:param VIP_color: str, color to use for VIP data (Default value = None)  
:param others_color: str, color for not VIP data (Default value = "white")  
:param include_all_inj_regions: bool (Default value = False)  
:param display_injection_volume: float, if True a spehere is added to display the injection coordinates and volume (Default value = True)

--------
## line: 334 - `get_streamlines`
  
```  
def get_streamlines(self, sl_file, color=None, *args, **kwargs):
```
>Render streamline data downloaded from https://neuroinformatics.nl/HBP/allen-connectivity-viewer/streamline-downloader.html  
:param sl_file: path to JSON file with streamliens data [or list of files]  
:param color: either a single color or a list of colors to color each streamline individually  
:param *args:  
:param **kwargs:

--------
## line: 387 - `get_projection_tracts_to_target`
  
```  
def get_projection_tracts_to_target(self, p0=None, **kwargs):
```
>Gets tractography data for all experiments whose projections reach the brain region or location of iterest.  
:param p0: list of 3 floats with XYZ coordinates of point to be used as seed (Default value = None)  
:param **kwargs: 

--------
## line: 415 - `download_streamlines_for_region`
  
```  
def download_streamlines_for_region(self, region, *args, **kwargs):
```
>Using the Allen Mouse Connectivity data and corresponding API, this function finds expeirments whose injectionswere targeted to the region of interest and downloads the corresponding streamlines data. By default, experiementsare selected for only WT mice and onl when the region was the primary injection target. Look at "ABA.experiments_source_search"to see how to change this behaviour.  
:param region: str with region to use for research  
:param *args: arguments for ABA.experiments_source_search  
:param **kwargs: arguments for ABA.experiments_source_search

--------
## line: 440 - `download_streamlines_to_region`
  
```  
def download_streamlines_to_region(self, p0, *args, mouse_line='wt', **kwargs):
```
>Using the Allen Mouse Connectivity data and corresponding API, this function finds injection experimentswhich resulted in fluorescence being found in the target point, then downloads the streamlines data.  
:param p0: list of floats with XYZ coordinates  
:param mouse_line: str with name of the mouse line to use(Default value = "wt")  
:param *args:   
:param **kwargs: 