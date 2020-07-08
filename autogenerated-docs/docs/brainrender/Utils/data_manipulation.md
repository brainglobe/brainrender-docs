



Contents
========

* [**`return_list_smart`** [#1]](#return_list_smart-1)
* [**`return_dict_smart`** [#15]](#return_dict_smart-15)
* [**`get_coords`** [#25]](#get_coords-25)
* [**`flatten_list`** [#66]](#flatten_list-66)
* [**`is_any_item_in_list`** [#82]](#is_any_item_in_list-82)
* [**`get_slice_coord`** [#98]](#get_slice_coord-98)


&nbsp;

--------
# **`return_list_smart`** [#1]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/Utils/data_manipulation.py#L1) online

```python
def return_list_smart(lst):
```

&nbsp;  
docstring:

```text
If the list has length > returns the list

if it has length == 1 it returns the element

if it has length == 0 it returns None

```

&nbsp;

--------
# **`return_dict_smart`** [#15]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/Utils/data_manipulation.py#L15) online

```python
def return_dict_smart(dct):
```

&nbsp;  
docstring:

no docstring

&nbsp;

--------
# **`get_coords`** [#25]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/Utils/data_manipulation.py#L25) online

```python
def get_coords(obj, mirror=False, mirror_ax='x'):
```

&nbsp;  
docstring:

```text
Takes coordinates in various format and turns them into what's
    expected from VTK plotter for rendering.

Can take a dict, Pandas Dataframe or Series

:param obj: dict, pandas.DataFrame or pandas.Series

:param mirror:  if True, the coordinates are mirrored around mirror_ax
    (Default value = False)

:param mirror_ax: ax to be used for mirroring ['x', 'y', 'z'] (Default
    value = 'x')

```

&nbsp;

--------
# **`flatten_list`** [#66]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/Utils/data_manipulation.py#L66) online

```python
def flatten_list(lst):
```

&nbsp;  
docstring:

```text
Flattens a list of lists

:param lst: list

```

&nbsp;

--------
# **`is_any_item_in_list`** [#82]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/Utils/data_manipulation.py#L82) online

```python
def is_any_item_in_list(L1, L2):
```

&nbsp;  
docstring:

```text
Checks if an item in a list is in another  list

:param L1:

:param L2:

```

&nbsp;

--------
# **`get_slice_coord`** [#98]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/Utils/data_manipulation.py#L98) online

```python
def get_slice_coord(bounds, n):
```

&nbsp;  
docstring:

```text
Given the bounds of an actor, return the point that

corresponds to the n% of the bounds range

:param bounds: should be a list of two floats

:param n: n should be a float in range 0, 1

```