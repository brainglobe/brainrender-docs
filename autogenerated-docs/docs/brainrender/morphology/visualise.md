



Contents
========

* [**MorphologyScene**](#morphologyscene)
	* [**`__init__`** [#35]](#__init__-35)
	* [**`_add_neurons_get_colors`** [#62]](#_add_neurons_get_colors-62)
	* [**`add_neurons`** [#180]](#add_neurons-180)


&nbsp;

--------
# **MorphologyScene**




&nbsp;
## **`__init__`** [#35]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/morphology/visualise.py#L35) online

```python
def __init__(self, *args, **kwargs):
```  


no docstring

&nbsp;
## **`_add_neurons_get_colors`** [#62]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/morphology/visualise.py#L62) online

```python
def _add_neurons_get_colors(self, neurons, color):
```  


```text
Parses color argument for self. Add_neurons
:para, neurons: list of neuron object or file paths. . .
:param color: default none.  can be:
- none: each neuron is colored according to the default color
- color: rbg, hex etc.  if a single color is passed all neurons will
    have that color
- cmap: str with name of a colormap: neurons are colored based on
    their sequential order and cmap
- dict: a dictionary specifying a color for soma, dendrites and axon
    actors, will be the same for all neurons
- list: a list of length = number of neurons with either a single
    color for each neuron
or a dictionary of colors for each neuron
```

&nbsp;
## **`add_neurons`** [#180]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/morphology/visualise.py#L180) online

```python
def add_neurons(self, neurons, color=None, display_axon=True,
    display_dendrites=True, alpha=1, neurite_radius=None):
```  


```text
Adds rendered morphological data of neurons reconstructions downloaded
    from the
mouse light project at janelia, neuromorpho. Org and other sources.
accepts neurons argument as:
- file(s) with morphological data
- vedo mesh actor(s) of neurons reconstructions
- dictionary or list of dictionary with actors for different neuron
    parts
:param self: instance of brainrender scene to use to render neurons
:param neurons: str, list, dict.  file(s) with neurons data or list of
    rendered neurons.
:param display_axon, display_dendrites: if set to false the
    corresponding neurite is not rendered
:param color: default none.  can be:
- none: each neuron is colored according to the default color
- color: rbg, hex etc.  if a single color is passed all neurons will
    have that color
- cmap: str with name of a colormap: neurons are colored based on
    their sequential order and cmap
- dict: a dictionary specifying a color for soma, dendrites and axon
    actors, will be the same for all neurons
- list: a list of length = number of neurons with either a single
    color for each neuron
or a dictionary of colors for each neuron
:param alpha: float in range 0,1.  neurons transparency
:param neurite_radius: float > 0 , radius of tube actor representing
    neurites
```