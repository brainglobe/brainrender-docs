# insects\_brains\_db

## Contents

* [**IBDB**](insects_brains_db.md#ibdb)
  * [**`__init__`** \[\#55\]](insects_brains_db.md#__init__-55)
  * [**`get_brain_id_from_species_name`** \[\#80\]](insects_brains_db.md#get_brain_id_from_species_name-80)
  * [**`get_structures_hierarchy`** \[\#97\]](insects_brains_db.md#get_structures_hierarchy-97)
  * [**`get_structures_reconstructions`** \[\#132\]](insects_brains_db.md#get_structures_reconstructions-132)
  * [**`get_brain`** \[\#216\]](insects_brains_db.md#get_brain-216)
  * [**`download_and_write_mesh`** \[\#245\]](insects_brains_db.md#download_and_write_mesh-245)
  * [**`make_root_mesh`** \[\#262\]](insects_brains_db.md#make_root_mesh-262)
  * [**`_get_structure_mesh`** \[\#281\]](insects_brains_db.md#_get_structure_mesh-281)
  * [**`_check_valid_region_arg`** \[\#315\]](insects_brains_db.md#_check_valid_region_arg-315)
  * [**`_check_obj_file`** \[\#326\]](insects_brains_db.md#_check_obj_file-326)
  * [**`get_region_color`** \[\#339\]](insects_brains_db.md#get_region_color-339)
  * [**`get_brain_regions`** \[\#368\]](insects_brains_db.md#get_brain_regions-368)
  * [**`add_descendants_to_tree`** \[\#98\]](insects_brains_db.md#add_descendants_to_tree-98)

## **IBDB**

### **`__init__`** \[\#55\]

Check the [_**`source code`**_](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/atlases/insects_brains_db.py#L55) online

```python
def __init__(self, species=None, sex=None, base_dir=None,
    make_root=True, **kwargs):
```

   
docstring:

no docstring

### **`get_brain_id_from_species_name`** \[\#80\]

Check the [_**`source code`**_](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/atlases/insects_brains_db.py#L80) online

```python
def get_brain_id_from_species_name(self, sel_species):
```

   
docstring:

no docstring

### **`get_structures_hierarchy`** \[\#97\]

Check the [_**`source code`**_](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/atlases/insects_brains_db.py#L97) online

```python
def get_structures_hierarchy(self):
```

   
docstring:

no docstring

### **`get_structures_reconstructions`** \[\#132\]

Check the [_**`source code`**_](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/atlases/insects_brains_db.py#L132) online

```python
def get_structures_reconstructions(self, species, sex):
```

   
docstring:

no docstring

### **`get_brain`** \[\#216\]

Check the [_**`source code`**_](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/atlases/insects_brains_db.py#L216) online

```python
def get_brain(self, species=None, sex=None):
```

   
docstring:

no docstring

### **`download_and_write_mesh`** \[\#245\]

Check the [_**`source code`**_](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/atlases/insects_brains_db.py#L245) online

```python
def download_and_write_mesh(self, acronym, obj_path):
```

   
docstring:

no docstring

### **`make_root_mesh`** \[\#262\]

Check the [_**`source code`**_](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/atlases/insects_brains_db.py#L262) online

```python
def make_root_mesh(self):
```

   
docstring:

no docstring

### **`_get_structure_mesh`** \[\#281\]

Check the [_**`source code`**_](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/atlases/insects_brains_db.py#L281) online

```python
def _get_structure_mesh(self, acronym, **kwargs):
```

   
docstring:

```text
Fetches the mesh for a brain region from the atlas.

:param acronym: string, acronym of brain region

:param **kwargs:
```

### **`_check_valid_region_arg`** \[\#315\]

Check the [_**`source code`**_](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/atlases/insects_brains_db.py#L315) online

```python
def _check_valid_region_arg(self, region):
```

   
docstring:

```text
Check that the string passed is a valid brain region name.
```

### **`_check_obj_file`** \[\#326\]

Check the [_**`source code`**_](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/atlases/insects_brains_db.py#L326) online

```python
def _check_obj_file(self, region, obj_file):
```

   
docstring:

```text
If the .obj file for a brain region hasn't been downloaded already,
    this function downloads it and writes it.

:param region: string, acronym of brain region

:param obj_file: path to .obj file to write downloaded data.
```

### **`get_region_color`** \[\#339\]

Check the [_**`source code`**_](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/atlases/insects_brains_db.py#L339) online

```python
def get_region_color(self, regions):
```

   
docstring:

```text
Gets the RGB color of a brain region from the atlas.

:param regions:  list of regions acronyms.
```

### **`get_brain_regions`** \[\#368\]

Check the [_**`source code`**_](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/atlases/insects_brains_db.py#L368) online

```python
def get_brain_regions(self, brain_regions, alpha=None, colors=None,
    use_original_color=True, **kwargs):
```

   
docstring:

no docstring

### **`add_descendants_to_tree`** \[\#98\]

Check the [_**`source code`**_](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/atlases/insects_brains_db.py#L98) online

```python
def add_descendants_to_tree(tree, structure, parent_id=None):
```

   
docstring:

```text
Recursively goes through all the the descendants of a region and adds
    them to the tree
```

