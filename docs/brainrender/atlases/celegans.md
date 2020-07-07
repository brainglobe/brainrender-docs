



Contents
========

* [**Celegans**](#celegans)
	* [line: 62 - `__init__`](#line-62---__init__)
	* [line: 84 - `_make_root`](#line-84---_make_root)
	* [line: 119 - `get_neurons_by`](#line-119---get_neurons_by)
	* [line: 151 - `get_neuron_color`](#line-151---get_neuron_color)
	* [line: 186 - `_get_data`](#line-186---_get_data)
	* [line: 249 - `_check_neuron_argument`](#line-249---_check_neuron_argument)
	* [line: 272 - `_parse_neuron_skeleton`](#line-272---_parse_neuron_skeleton)
	* [line: 308 - `_get_structure_mesh`](#line-308---_get_structure_mesh)
	* [line: 329 - `get_neurons`](#line-329---get_neurons)
	* [line: 371 - `get_neurons_synapses`](#line-371---get_neurons_synapses)
	* [line: 518 - `dist`](#line-518---dist)
	* [line: 525 - `get_point`](#line-525---get_point)


&nbsp;

--------

--------
# **Celegans**




--------
## line: 62 - `__init__`
  
```  
def __init__(self, data_folder=None, base_dir=None, **kwargs):
```
>This class handles loading and parsing neuroanatomical data for the C. elegans connectome from https://www.biorxiv.org/content/10.1101/2020.04.30.066209v1  
:param base_dir: path to directory to use for saving data (default value None)  
:param kwargs: can be used to pass path to individual data folders. See brainrender/Utils/paths_manager.py  
:param data_folder: str, path to a folder with data for the connectome # TODO replace with downloading data

--------
## line: 84 - `_make_root`
  
```  
def _make_root(self, rootpath):
```
>Creates a root mesh by merging the mesh corresponding to each neuron,then saves it as an obj file at rootpath

--------
## line: 119 - `get_neurons_by`
  
```  
def get_neurons_by(self, getby='pair', lookup=None):
```
>Selects a subset of the neurons using some criteria and lookup key, based on the neurons metadata  
:param getby: str, name of the metadata key to use for selecting neurons  
:param lookup: str/int.. neurons whose attribute 'getby' matches the lookup value will be selected:returns: list of strings with neurons names

--------
## line: 151 - `get_neuron_color`
  
```  
def get_neuron_color(self, neuron, colorby='type'):
```
>Get a neuron's RGB color. Colors can be assigned based on different criterialike the neuron's type or by individual neuron etc...  
:param neuron: str, nueron name  
:param colorby: str, metadata attribute to use for coloring:returns: rgb values of color

--------
## line: 186 - `_get_data`
  
```  
def _get_data(self):
```
>Loads data and metadata for the C. elegans connectome.

--------
## line: 249 - `_check_neuron_argument`
  
```  
def _check_neuron_argument(self, neurons):
```
>Checks if a list of string includes neurons name, returns onlyelements of the list that are correct names  
:param neurons: list of strings with neurons names

--------
## line: 272 - `_parse_neuron_skeleton`
  
```  
def _parse_neuron_skeleton(self, neuron):
```
>Parses a neuron's skeleton information from skeleton .json fileto create a vtk actor that represents the neuron  
:param neuron: str, neuron name

--------
## line: 308 - `_get_structure_mesh`
  
```  
def _get_structure_mesh(self, acronym, **kwargs):
```
>Get's the mesh for a brainregion, for this atlas it's just forgetting/making the root mesh

--------
## line: 329 - `get_neurons`
  
```  
def get_neurons(self, neurons, alpha=1, as_skeleton=False, colorby='type'):
```
>Renders neurons and adds returns to the scene.   
:param neurons: list of names of neurons  
:param alpha: float in range 0,1 -  neurons transparency  
:param as_skeleton: bool (Default value = False), if True neurons are rendered as skeletons                     otherwise as a full mesh showing the whole morphology  
:param colorby: str, criteria to use to color the neurons. Accepts values like type, individual etc. 

--------
## line: 371 - `get_neurons_synapses`
  
```  
def get_neurons_synapses(self, scene_store, neurons, alpha=1, pre=False, post=False, colorby='synapse_type', draw_patches=False, draw_arrows=True):
```
>THIS METHODS GETS CALLED BY SCENE, self referes to the instance of Scene not to this class.Renders neurons and adds them to the scene.   
:param neurons: list of names of neurons  
:param alpha: float in range 0,1 -  neurons transparency  
:param pre: bool, if True the presynaptic sites of each neuron are rendered  
:param post: bool, if True the postsynaptic sites on each neuron are rendered  
:param colorby: str, criteria to use to color the neurons.                 Accepts values like synapse_type, type, individual etc.   
:param draw_patches: bool, default True. If true dark patches are used to show the location of post synapses  
:param draw_arrows: bool, default True. If true arrows are used to show the location of post synapses

--------
## line: 518 - `dist`
  
```  
def dist(p1, p2):
```


>  no docstring

--------
## line: 525 - `get_point`
  
```  
def get_point(p1, p2, d, u):
```


>  no docstring