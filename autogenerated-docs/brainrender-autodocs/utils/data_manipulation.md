# data\_manipulation

## Contents

* [**`return_list_smart`** \[\#1\]](data_manipulation.md#return_list_smart-1)
* [**`return_dict_smart`** \[\#15\]](data_manipulation.md#return_dict_smart-15)
* [**`get_coords`** \[\#25\]](data_manipulation.md#get_coords-25)
* [**`flatten_list`** \[\#66\]](data_manipulation.md#flatten_list-66)
* [**`is_any_item_in_list`** \[\#82\]](data_manipulation.md#is_any_item_in_list-82)
* [**`get_slice_coord`** \[\#98\]](data_manipulation.md#get_slice_coord-98)

## **`return_list_smart`** \[\#1\]

Check the [_**`source code`**_](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/Utils/data_manipulation.py#L1) online

```python
def return_list_smart(lst):
```

   
docstring:

```text
If the list has length > returns the list

if it has length == 1 it returns the element

if it has length == 0 it returns None
```

## **`return_dict_smart`** \[\#15\]

Check the [_**`source code`**_](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/Utils/data_manipulation.py#L15) online

```python
def return_dict_smart(dct):
```

   
docstring:

no docstring

## **`get_coords`** \[\#25\]

Check the [_**`source code`**_](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/Utils/data_manipulation.py#L25) online

```python
def get_coords(obj, mirror=False, mirror_ax='x'):
```

   
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

## **`flatten_list`** \[\#66\]

Check the [_**`source code`**_](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/Utils/data_manipulation.py#L66) online

```python
def flatten_list(lst):
```

   
docstring:

```text
Flattens a list of lists

:param lst: list
```

## **`is_any_item_in_list`** \[\#82\]

Check the [_**`source code`**_](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/Utils/data_manipulation.py#L82) online

```python
def is_any_item_in_list(L1, L2):
```

   
docstring:

```text
Checks if an item in a list is in another  list

:param L1:

:param L2:
```

## **`get_slice_coord`** \[\#98\]

Check the [_**`source code`**_](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/Utils/data_manipulation.py#L98) online

```python
def get_slice_coord(bounds, n):
```

   
docstring:

```text
Given the bounds of an actor, return the point that

corresponds to the n% of the bounds range

:param bounds: should be a list of two floats

:param n: n should be a float in range 0, 1
```

