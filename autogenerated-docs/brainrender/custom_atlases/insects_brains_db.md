



Contents
========

* [**IBDB**](#ibdb)
	* [**`__init__`** [#55]](#__init__-55)
	* [**`get_brain_id_from_species_name`** [#80]](#get_brain_id_from_species_name-80)
	* [**`get_structures_hierarchy`** [#97]](#get_structures_hierarchy-97)
	* [**`get_structures_reconstructions`** [#132]](#get_structures_reconstructions-132)
	* [**`get_brain`** [#216]](#get_brain-216)
	* [**`download_and_write_mesh`** [#245]](#download_and_write_mesh-245)
	* [**`make_root_mesh`** [#262]](#make_root_mesh-262)
	* [**`_get_structure_mesh`** [#281]](#_get_structure_mesh-281)
	* [**`_check_valid_region_arg`** [#315]](#_check_valid_region_arg-315)
	* [**`_check_obj_file`** [#326]](#_check_obj_file-326)
	* [**`get_region_color`** [#339]](#get_region_color-339)
	* [**`get_brain_regions`** [#368]](#get_brain_regions-368)
	* [**`add_descendants_to_tree`** [#98]](#add_descendants_to_tree-98)


&nbsp;

--------
# **IBDB**




&nbsp;
## **`__init__`** [#55]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/custom_atlases/insects_brains_db.py#L55) online

```python
def __init__(self, species=None, sex=None, base_dir=None,
    make_root=True, **kwargs):
```

&nbsp;  
docstring:

no docstring

&nbsp;
## **`get_brain_id_from_species_name`** [#80]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/custom_atlases/insects_brains_db.py#L80) online

```python
def get_brain_id_from_species_name(self, sel_species):
```

&nbsp;  
docstring:

no docstring

&nbsp;
## **`get_structures_hierarchy`** [#97]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/custom_atlases/insects_brains_db.py#L97) online

```python
def get_structures_hierarchy(self):
```

&nbsp;  
docstring:

no docstring

&nbsp;
## **`get_structures_reconstructions`** [#132]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/custom_atlases/insects_brains_db.py#L132) online

```python
def get_structures_reconstructions(self, species, sex):
```

&nbsp;  
docstring:

no docstring

&nbsp;
## **`get_brain`** [#216]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/custom_atlases/insects_brains_db.py#L216) online

```python
def get_brain(self, species=None, sex=None):
```

&nbsp;  
docstring:

no docstring

&nbsp;
## **`download_and_write_mesh`** [#245]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/custom_atlases/insects_brains_db.py#L245) online

```python
def download_and_write_mesh(self, acronym, obj_path):
```

&nbsp;  
docstring:

no docstring

&nbsp;
## **`make_root_mesh`** [#262]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/custom_atlases/insects_brains_db.py#L262) online

```python
def make_root_mesh(self):
```

&nbsp;  
docstring:

no docstring

&nbsp;
## **`_get_structure_mesh`** [#281]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/custom_atlases/insects_brains_db.py#L281) online

```python
def _get_structure_mesh(self, acronym, **kwargs):
```

&nbsp;  
docstring:

```text
Fetches the mesh for a brain region from the atlas.

:param acronym: string, acronym of brain region

:param **kwargs:

```

&nbsp;
## **`_check_valid_region_arg`** [#315]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/custom_atlases/insects_brains_db.py#L315) online

```python
def _check_valid_region_arg(self, region):
```

&nbsp;  
docstring:

```text
Check that the string passed is a valid brain region name.

```

&nbsp;
## **`_check_obj_file`** [#326]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/custom_atlases/insects_brains_db.py#L326) online

```python
def _check_obj_file(self, region, obj_file):
```

&nbsp;  
docstring:

```text
If the .obj file for a brain region hasn't been downloaded already,
    this function downloads it and writes it.

:param region: string, acronym of brain region

:param obj_file: path to .obj file to write downloaded data.

```

&nbsp;
## **`get_region_color`** [#339]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/custom_atlases/insects_brains_db.py#L339) online

```python
def get_region_color(self, regions):
```

&nbsp;  
docstring:

```text
Gets the RGB color of a brain region from the atlas.

:param regions:  list of regions acronyms.

```

&nbsp;
## **`get_brain_regions`** [#368]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/custom_atlases/insects_brains_db.py#L368) online

```python
def get_brain_regions(self, brain_regions, alpha=None, colors=None,
    use_original_color=True, **kwargs):
```

&nbsp;  
docstring:

no docstring

&nbsp;
## **`add_descendants_to_tree`** [#98]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/custom_atlases/insects_brains_db.py#L98) online

```python
def add_descendants_to_tree(tree, structure, parent_id=None):
```

&nbsp;  
docstring:

```text
Recursively goes through all the the descendants of a region and adds
    them to the tree

```