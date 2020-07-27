



Contents
========

* [**`return_list_smart`** [#6]](#return_list_smart-6)
* [**`return_dict_smart`** [#20]](#return_dict_smart-20)
* [**`is_any_item_in_list`** [#30]](#is_any_item_in_list-30)
* [**`get_slice_coord`** [#51]](#get_slice_coord-51)
* [**`make_optic_canula_cylinder`** [#80]](#make_optic_canula_cylinder-80)
* [**`get_cells_in_region`** [#134]](#get_cells_in_region-134)


&nbsp;

--------
# **`return_list_smart`** [#6]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/Utils/data_manipulation.py#L6) online

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
# **`return_dict_smart`** [#20]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/Utils/data_manipulation.py#L20) online

```python
def return_dict_smart(dct):
```

&nbsp;  
docstring:

no docstring

&nbsp;

--------
# **`is_any_item_in_list`** [#30]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/Utils/data_manipulation.py#L30) online

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
# **`get_slice_coord`** [#51]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/Utils/data_manipulation.py#L51) online

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

&nbsp;

--------
# **`make_optic_canula_cylinder`** [#80]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/Utils/data_manipulation.py#L80) online

```python
def make_optic_canula_cylinder(atlas, root, target_region=None,
    pos=None, offsets=(0, 0, (- 500)), hemisphere='right',
    color='powderblue', radius=350, alpha=0.5, **kwargs):
```

&nbsp;  
docstring:

```text
Creates a cylindrical vedo actor to scene to render optic cannulas. By
    default

this is a semi-transparent blue cylinder centered on the center of
    mass of

a specified target region and oriented vertically.

:param target_region: str, acronym of target region to extract
    coordinates

of implanted fiber. By defualt the fiber will be centered on the
    center

of mass of the target region but the offset arguments can be used to

fine tune the position. Alternative pass a 'pos' argument with AP-DV-
    ML coords.

:param pos: list or tuple or np.array with X,Y,Z coordinates. Must
    have length = 3.

:param x_offset, y_offset, z_offset: int, used to fine tune the
    coordinates of

the implanted cannula.

:param **kwargs: used to specify which hemisphere the cannula is and
    parameters

of the rendered cylinder: color, alpha, rotation axis...

```

&nbsp;

--------
# **`get_cells_in_region`** [#134]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/Utils/data_manipulation.py#L134) online

```python
def get_cells_in_region(atlas, cells, region):
```

&nbsp;  
docstring:

```text
Selects the cells that are in a list of user provided

brain regions from a dataframe of cell locations

:param cells: pd.DataFrame of cells x,y,z coordinates

```