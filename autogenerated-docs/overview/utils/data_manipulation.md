# data\_manipulation

## Contents

* [line: 1 - `return_list_smart`](data_manipulation.md#line-1---return_list_smart)
* [line: 15 - `return_dict_smart`](data_manipulation.md#line-15---return_dict_smart)
* [line: 25 - `get_coords`](data_manipulation.md#line-25---get_coords)
* [line: 66 - `flatten_list`](data_manipulation.md#line-66---flatten_list)
* [line: 82 - `is_any_item_in_list`](data_manipulation.md#line-82---is_any_item_in_list)
* [line: 98 - `get_slice_coord`](data_manipulation.md#line-98---get_slice_coord)

## line: 1 - `return_list_smart`

```text
def return_list_smart(lst):
```

> If the list has length &gt; returns the listif it has length == 1 it returns the elementif it has length == 0 it returns None

## line: 15 - `return_dict_smart`

```text
def return_dict_smart(dct):
```

> no docstring

## line: 25 - `get_coords`

```text
def get_coords(obj, mirror=False, mirror_ax='x'):
```

> Takes coordinates in various format and turns them into what's expected from VTK plotter for rendering. Can take a dict, Pandas Dataframe or Series  
> :param obj: dict, pandas.DataFrame or pandas.Series  
> :param mirror: if True, the coordinates are mirrored around mirror\_ax \(Default value = False\)  
> :param mirror\_ax: ax to be used for mirroring \['x', 'y', 'z'\] \(Default value = 'x'\)

## line: 66 - `flatten_list`

```text
def flatten_list(lst):
```

> Flattens a list of lists  
> :param lst: list

## line: 82 - `is_any_item_in_list`

```text
def is_any_item_in_list(L1, L2):
```

> Checks if an item in a list is in another list  
> :param L1:  
> :param L2:

## line: 98 - `get_slice_coord`

```text
def get_slice_coord(bounds, n):
```

> Given the bounds of an actor, return the point thatcorresponds to the n% of the bounds range  
> :param bounds: should be a list of two floats  
> :param n: n should be a float in range 0, 1

