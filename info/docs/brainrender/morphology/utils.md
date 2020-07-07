



Contents
========

* [line: 11 - `get_neuron_actors_with_morphapi`](#line-11---get_neuron_actors_with_morphapi)
* [line: 50 - `edit_neurons`](#line-50---edit_neurons)


&nbsp;

--------
# line: 11 - `get_neuron_actors_with_morphapi`
  
```  
def get_neuron_actors_with_morphapi(swcfile=None, neuron=None, neurite_radius=None, use_cache=True, soma_radius=None):
```


>  no docstring

&nbsp;

--------
# line: 50 - `edit_neurons`
  
```  
def edit_neurons(neurons, **kwargs):
```
>    Modify neurons actors after they have been created, at render time.    neurons should be a list of dictionaries with soma, dendrite and axon actors of each neuron.  
:param neurons: list of dictionaries with vtk actors for each neuron  
:param **kwargs: 