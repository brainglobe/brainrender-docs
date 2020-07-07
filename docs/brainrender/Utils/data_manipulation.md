



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
  
```  
def return_list_smart(lst):
```
>If the list has length > returns the listif it has length == 1 it returns the elementif it has length == 0 it returns None

&nbsp;

--------
# line: 15 - `return_dict_smart`
  
```  
def return_dict_smart(dct):
```


>  no docstring

&nbsp;

--------
# line: 25 - `get_coords`
  
```  
def get_coords(obj, mirror=False, mirror_ax='x'):
```
>Takes coordinates in various format and turns them into what's expected from VTK plotter for rendering. Can take a dict, Pandas Dataframe or Series  
:param obj: dict, pandas.DataFrame or pandas.Series  
:param mirror:  if True, the coordinates are mirrored around mirror_ax (Default value = False)  
:param mirror_ax: ax to be used for mirroring ['x', 'y', 'z'] (Default value = 'x')

&nbsp;

--------
# line: 66 - `flatten_list`
  
```  
def flatten_list(lst):
```
>Flattens a list of lists  
:param lst: list

&nbsp;

--------
# line: 82 - `is_any_item_in_list`
  
```  
def is_any_item_in_list(L1, L2):
```
>Checks if an item in a list is in another  list  
:param L1:   
:param L2: 

&nbsp;

--------
# line: 98 - `get_slice_coord`
  
```  
def get_slice_coord(bounds, n):
```
>Given the bounds of an actor, return the point thatcorresponds to the n% of the bounds range  
:param bounds: should be a list of two floats  
:param n: n should be a float in range 0, 1