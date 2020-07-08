



Contents
========

* [line: 1 - `return_list_smart`](#line-1---return_list_smart)
* [line: 15 - `return_dict_smart`](#line-15---return_dict_smart)
* [line: 25 - `get_coords`](#line-25---get_coords)
* [line: 66 - `flatten_list`](#line-66---flatten_list)
* [line: 82 - `is_any_item_in_list`](#line-82---is_any_item_in_list)
* [line: 98 - `get_slice_coord`](#line-98---get_slice_coord)


&nbsp;

--------
# line: 1 - `return_list_smart`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/Utils/data_manipulation.py#L1) online
#### function definition


```python
def return_list_smart(lst):
```
##### docstring
  


```python

"""
    If the list has length > returns the list
    if it has length == 1 it returns the element
    if it has length == 0 it returns None
"""
```

&nbsp;

--------
# line: 15 - `return_dict_smart`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/Utils/data_manipulation.py#L15) online
#### function definition


```python
def return_dict_smart(dct):
```
##### docstring
  


```python

"""
 no docstring 
"""
```

&nbsp;

--------
# line: 25 - `get_coords`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/Utils/data_manipulation.py#L25) online
#### function definition


```python
def get_coords(obj, mirror=False, mirror_ax='x'):
```
##### docstring
  


```python

"""
    Takes coordinates in various format and turns them into what's expected from VTK plotter for rendering. 
    Can take a dict, Pandas Dataframe or Series
    
    :param obj: dict, pandas.DataFrame or pandas.Series
    :param mirror:  if True, the coordinates are mirrored around mirror_ax (Default value = False)
    :param mirror_ax: ax to be used for mirroring ['x', 'y', 'z'] (Default value = 'x')
"""
```

&nbsp;

--------
# line: 66 - `flatten_list`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/Utils/data_manipulation.py#L66) online
#### function definition


```python
def flatten_list(lst):
```
##### docstring
  


```python

"""
    Flattens a list of lists
    
    :param lst: list
"""
```

&nbsp;

--------
# line: 82 - `is_any_item_in_list`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/Utils/data_manipulation.py#L82) online
#### function definition


```python
def is_any_item_in_list(L1, L2):
```
##### docstring
  


```python

"""
    Checks if an item in a list is in another  list
    
    :param L1: 
    :param L2: 
"""
```

&nbsp;

--------
# line: 98 - `get_slice_coord`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/Utils/data_manipulation.py#L98) online
#### function definition


```python
def get_slice_coord(bounds, n):
```
##### docstring
  


```python

"""
    Given the bounds of an actor, return the point that
    corresponds to the n% of the bounds range
    
    
    :param bounds: should be a list of two floats
    :param n: n should be a float in range 0, 1
"""
```