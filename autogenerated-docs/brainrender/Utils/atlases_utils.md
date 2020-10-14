



Contents
========

* [**`parse_neurons_colors`** [#11]](#parse_neurons_colors-11)


&nbsp;

--------
# **`parse_neurons_colors`** [#11]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/Utils/atlases_utils.py#L11) online

```python
def parse_neurons_colors(neurons, color):
```

&nbsp;  
docstring:

```text
Prepares the color info to render neurons

:param neurons: str, list, dict. File(s) with neurons data or list of
    rendered neurons.

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

```