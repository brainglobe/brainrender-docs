# visualise

## Contents

* [**MorphologyScene**](visualise.md#morphologyscene)
  * [line: 35 - `__init__`](visualise.md#line-35---__init__)
  * [line: 62 - `_add_neurons_get_colors`](visualise.md#line-62---_add_neurons_get_colors)
  * [line: 180 - `add_neurons`](visualise.md#line-180---add_neurons)

## **MorphologyScene**

### line: 35 - `__init__`

```text
def __init__(self, *args, **kwargs):
```

> no docstring

### line: 62 - `_add_neurons_get_colors`

```text
def _add_neurons_get_colors(self, neurons, color):
```

> Parses color argument for self.add\_neurons:para, neurons: list of Neuron object or file paths...  
> :param color: default None. Can be: - None: each neuron is colored according to the default color - color: rbg, hex etc. If a single color is passed all neurons will have that color - cmap: str with name of a colormap: neurons are colored based on their sequential order and cmap - dict: a dictionary specifying a color for soma, dendrites and axon actors, will be the same for all neurons - list: a list of length = number of neurons with either a single color for each neuron or a dictionary of colors for each neuron

### line: 180 - `add_neurons`

```text
def add_neurons(self, neurons, color=None, display_axon=True, display_dendrites=True, alpha=1, neurite_radius=None):
```

> Adds rendered morphological data of neurons reconstructions downloaded from theMouse Light project at Janelia, neuromorpho.org and other sources. Accepts neurons argument as: - file\(s\) with morphological data - vedo mesh actor\(s\) of neurons reconstructions - dictionary or list of dictionary with actors for different neuron parts  
> :param self: instance of brainrender Scene to use to render neurons  
> :param neurons: str, list, dict. File\(s\) with neurons data or list of rendered neurons.  
> :param display\_axon, display\_dendrites: if set to False the corresponding neurite is not rendered  
> :param color: default None. Can be: - None: each neuron is colored according to the default color - color: rbg, hex etc. If a single color is passed all neurons will have that color - cmap: str with name of a colormap: neurons are colored based on their sequential order and cmap - dict: a dictionary specifying a color for soma, dendrites and axon actors, will be the same for all neurons - list: a list of length = number of neurons with either a single color for each neuron or a dictionary of colors for each neuron  
> :param alpha: float in range 0,1. Neurons transparency  
> :param neurite\_radius: float &gt; 0 , radius of tube actor representing neurites

