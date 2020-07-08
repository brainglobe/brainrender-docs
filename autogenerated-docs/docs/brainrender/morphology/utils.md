



Contents
========

* [line: 11 `get_neuron_actors_with_morphapi`](#line-11-get_neuron_actors_with_morphapi)
* [line: 50 `edit_neurons`](#line-50-edit_neurons)


&nbsp;

--------
# line: 11 `get_neuron_actors_with_morphapi`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/morphology/utils.py#L11) online
#### function definition


```python
def get_neuron_actors_with_morphapi(swcfile=None, neuron=None, neurite_radius=None, use_cache=True, soma_radius=None):
```
##### docstring
  


```python

"""
 no docstring 
"""
```

&nbsp;

--------
# line: 50 `edit_neurons`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/morphology/utils.py#L50) online
#### function definition


```python
def edit_neurons(neurons, **kwargs):
```
##### docstring
  


```python

"""
        Modify neurons actors after they have been created, at render time.
        neurons should be a list of dictionaries with soma, dendrite and axon actors of each neuron.
    :param neurons: list of dictionaries with vtk actors for each neuron
    :param **kwargs: 
"""
```