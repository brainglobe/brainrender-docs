



Contents
========

* [**IBDB**](#ibdb)
* [line: 55 `__init__`](#line-55-__init__)
* [line: 80 `get_brain_id_from_species_name`](#line-80-get_brain_id_from_species_name)
* [line: 97 `get_structures_hierarchy`](#line-97-get_structures_hierarchy)
* [line: 132 `get_structures_reconstructions`](#line-132-get_structures_reconstructions)
* [line: 216 `get_brain`](#line-216-get_brain)
* [line: 245 `download_and_write_mesh`](#line-245-download_and_write_mesh)
* [line: 262 `make_root_mesh`](#line-262-make_root_mesh)
* [line: 281 `_get_structure_mesh`](#line-281-_get_structure_mesh)
* [line: 315 `_check_valid_region_arg`](#line-315-_check_valid_region_arg)
* [line: 326 `_check_obj_file`](#line-326-_check_obj_file)
* [line: 339 `get_region_color`](#line-339-get_region_color)
* [line: 368 `get_brain_regions`](#line-368-get_brain_regions)
* [line: 98 `add_descendants_to_tree`](#line-98-add_descendants_to_tree)


&nbsp;

--------

--------
# **IBDB**




&nbsp;

--------
# line: 55 `__init__`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/atlases/insects_brains_db.py#L55) online
#### function definition


```python
def __init__(self, species=None, sex=None, base_dir=None, make_root=True, **kwargs):
```
##### docstring
  


```python

"""
 no docstring 
"""
```

&nbsp;

--------
# line: 80 `get_brain_id_from_species_name`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/atlases/insects_brains_db.py#L80) online
#### function definition


```python
def get_brain_id_from_species_name(self, sel_species):
```
##### docstring
  


```python

"""
 no docstring 
"""
```

&nbsp;

--------
# line: 97 `get_structures_hierarchy`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/atlases/insects_brains_db.py#L97) online
#### function definition


```python
def get_structures_hierarchy(self):
```
##### docstring
  


```python

"""
 no docstring 
"""
```

&nbsp;

--------
# line: 132 `get_structures_reconstructions`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/atlases/insects_brains_db.py#L132) online
#### function definition


```python
def get_structures_reconstructions(self, species, sex):
```
##### docstring
  


```python

"""
 no docstring 
"""
```

&nbsp;

--------
# line: 216 `get_brain`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/atlases/insects_brains_db.py#L216) online
#### function definition


```python
def get_brain(self, species=None, sex=None):
```
##### docstring
  


```python

"""
 no docstring 
"""
```

&nbsp;

--------
# line: 245 `download_and_write_mesh`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/atlases/insects_brains_db.py#L245) online
#### function definition


```python
def download_and_write_mesh(self, acronym, obj_path):
```
##### docstring
  


```python

"""
 no docstring 
"""
```

&nbsp;

--------
# line: 262 `make_root_mesh`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/atlases/insects_brains_db.py#L262) online
#### function definition


```python
def make_root_mesh(self):
```
##### docstring
  


```python

"""
 no docstring 
"""
```

&nbsp;

--------
# line: 281 `_get_structure_mesh`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/atlases/insects_brains_db.py#L281) online
#### function definition


```python
def _get_structure_mesh(self, acronym, **kwargs):
```
##### docstring
  


```python

"""
    Fetches the mesh for a brain region from the atlas.
    
    :param acronym: string, acronym of brain region
    :param **kwargs:
"""
```

&nbsp;

--------
# line: 315 `_check_valid_region_arg`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/atlases/insects_brains_db.py#L315) online
#### function definition


```python
def _check_valid_region_arg(self, region):
```
##### docstring
  


```python

"""
    Check that the string passed is a valid brain region name.
"""
```

&nbsp;

--------
# line: 326 `_check_obj_file`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/atlases/insects_brains_db.py#L326) online
#### function definition


```python
def _check_obj_file(self, region, obj_file):
```
##### docstring
  


```python

"""
    If the .obj file for a brain region hasn't been downloaded already, this function downloads it and writes it.
    
    :param region: string, acronym of brain region
    :param obj_file: path to .obj file to write downloaded data.
"""
```

&nbsp;

--------
# line: 339 `get_region_color`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/atlases/insects_brains_db.py#L339) online
#### function definition


```python
def get_region_color(self, regions):
```
##### docstring
  


```python

"""
    Gets the RGB color of a brain region from the atlas.
    
    :param regions:  list of regions acronyms.
"""
```

&nbsp;

--------
# line: 368 `get_brain_regions`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/atlases/insects_brains_db.py#L368) online
#### function definition


```python
def get_brain_regions(self, brain_regions, alpha=None, colors=None, use_original_color=True, **kwargs):
```
##### docstring
  


```python

"""
 no docstring 
"""
```

&nbsp;

--------
# line: 98 `add_descendants_to_tree`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/atlases/insects_brains_db.py#L98) online
#### function definition


```python
def add_descendants_to_tree(tree, structure, parent_id=None):
```
##### docstring
  


```python

"""
    Recursively goes through all the the descendants of a region and adds them to the tree
"""
```