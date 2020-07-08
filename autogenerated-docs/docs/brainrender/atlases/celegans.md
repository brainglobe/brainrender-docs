



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




&nbsp;

--------
# line: 62 - `__init__`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/atlases/celegans.py#L62) online
#### function definition


```python
def __init__(self, data_folder=None, base_dir=None, **kwargs):
```
##### docstring
  


```python

"""
    This class handles loading and parsing neuroanatomical data for the C. elegans connectome from 
    https://www.biorxiv.org/content/10.1101/2020.04.30.066209v1
    
    :param base_dir: path to directory to use for saving data (default value None)
    :param kwargs: can be used to pass path to individual data folders. See brainrender/Utils/paths_manager.py
    :param data_folder: str, path to a folder with data for the connectome # TODO replace with downloading data
"""
```

&nbsp;

--------
# line: 84 - `_make_root`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/atlases/celegans.py#L84) online
#### function definition


```python
def _make_root(self, rootpath):
```
##### docstring
  


```python

"""
    Creates a root mesh by merging the mesh corresponding to each neuron,
    then saves it as an obj file at rootpath
"""
```

&nbsp;

--------
# line: 119 - `get_neurons_by`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/atlases/celegans.py#L119) online
#### function definition


```python
def get_neurons_by(self, getby='pair', lookup=None):
```
##### docstring
  


```python

"""
    Selects a subset of the neurons using some criteria and lookup key, 
    based on the neurons metadata
    
    :param getby: str, name of the metadata key to use for selecting neurons
    :param lookup: str/int.. neurons whose attribute 'getby' matches the lookup value will be selected
    
    :returns: list of strings with neurons names
"""
```

&nbsp;

--------
# line: 151 - `get_neuron_color`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/atlases/celegans.py#L151) online
#### function definition


```python
def get_neuron_color(self, neuron, colorby='type'):
```
##### docstring
  


```python

"""
    Get a neuron's RGB color. Colors can be assigned based on different criteria
    like the neuron's type or by individual neuron etc...
    
    :param neuron: str, nueron name
    :param colorby: str, metadata attribute to use for coloring
    :returns: rgb values of color
"""
```

&nbsp;

--------
# line: 186 - `_get_data`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/atlases/celegans.py#L186) online
#### function definition


```python
def _get_data(self):
```
##### docstring
  


```python

"""
    Loads data and metadata for the C. elegans connectome.
"""
```

&nbsp;

--------
# line: 249 - `_check_neuron_argument`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/atlases/celegans.py#L249) online
#### function definition


```python
def _check_neuron_argument(self, neurons):
```
##### docstring
  


```python

"""
    Checks if a list of string includes neurons name, returns only
    elements of the list that are correct names
    
    :param neurons: list of strings with neurons names
"""
```

&nbsp;

--------
# line: 272 - `_parse_neuron_skeleton`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/atlases/celegans.py#L272) online
#### function definition


```python
def _parse_neuron_skeleton(self, neuron):
```
##### docstring
  


```python

"""
    Parses a neuron's skeleton information from skeleton .json file
    to create a vtk actor that represents the neuron
    
    :param neuron: str, neuron name
"""
```

&nbsp;

--------
# line: 308 - `_get_structure_mesh`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/atlases/celegans.py#L308) online
#### function definition


```python
def _get_structure_mesh(self, acronym, **kwargs):
```
##### docstring
  


```python

"""
    Get's the mesh for a brainregion, for this atlas it's just for
    getting/making the root mesh
"""
```

&nbsp;

--------
# line: 329 - `get_neurons`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/atlases/celegans.py#L329) online
#### function definition


```python
def get_neurons(self, neurons, alpha=1, as_skeleton=False, colorby='type'):
```
##### docstring
  


```python

"""
    Renders neurons and adds returns to the scene. 
    
    :param neurons: list of names of neurons
    :param alpha: float in range 0,1 -  neurons transparency
    :param as_skeleton: bool (Default value = False), if True neurons are rendered as skeletons 
                        otherwise as a full mesh showing the whole morphology
    :param colorby: str, criteria to use to color the neurons. Accepts values like type, individual etc. 
"""
```

&nbsp;

--------
# line: 371 - `get_neurons_synapses`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/atlases/celegans.py#L371) online
#### function definition


```python
def get_neurons_synapses(self, scene_store, neurons, alpha=1, pre=False, post=False, colorby='synapse_type', draw_patches=False, draw_arrows=True):
```
##### docstring
  


```python

"""
    THIS METHODS GETS CALLED BY SCENE, self referes to the instance of Scene not to this class.
    Renders neurons and adds them to the scene. 
    
    :param neurons: list of names of neurons
    :param alpha: float in range 0,1 -  neurons transparency
    :param pre: bool, if True the presynaptic sites of each neuron are rendered
    :param post: bool, if True the postsynaptic sites on each neuron are rendered
    :param colorby: str, criteria to use to color the neurons.
                     Accepts values like synapse_type, type, individual etc. 
    :param draw_patches: bool, default True. If true dark patches are used to show the location of post synapses
    :param draw_arrows: bool, default True. If true arrows are used to show the location of post synapses
"""
```

&nbsp;

--------
# line: 518 - `dist`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/atlases/celegans.py#L518) online
#### function definition


```python
def dist(p1, p2):
```
##### docstring
  


```python

"""
 no docstring 
"""
```

&nbsp;

--------
# line: 525 - `get_point`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/atlases/celegans.py#L525) online
#### function definition


```python
def get_point(p1, p2, d, u):
```
##### docstring
  


```python

"""
 no docstring 
"""
```