# utils

## Contents

* [**`get_neuron_actors_with_morphapi`** \[\#11\]](utils.md#get_neuron_actors_with_morphapi-11)
* [**`edit_neurons`** \[\#50\]](utils.md#edit_neurons-50)

## **`get_neuron_actors_with_morphapi`** \[\#11\]

Check the [_**`source code`**_](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/morphology/utils.py#L11) online

```python
def get_neuron_actors_with_morphapi(swcfile=None, neuron=None,
    neurite_radius=None, use_cache=True, soma_radius=None):
```

   
docstring:

no docstring

## **`edit_neurons`** \[\#50\]

Check the [_**`source code`**_](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/morphology/utils.py#L50) online

```python
def edit_neurons(neurons, **kwargs):
```

   
docstring:

```text
Modify neurons actors after they have been created, at render time.

neurons should be a list of dictionaries with soma, dendrite and axon
    actors of each neuron.

:param neurons: list of dictionaries with vtk actors for each neuron

:param **kwargs:
```

