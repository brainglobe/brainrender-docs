# insects\_brains\_db

## Contents

* [**IBDB**](insects_brains_db.md#ibdb)
  * [line: 55 - `__init__`](insects_brains_db.md#line-55---__init__)
  * [line: 80 - `get_brain_id_from_species_name`](insects_brains_db.md#line-80---get_brain_id_from_species_name)
  * [line: 97 - `get_structures_hierarchy`](insects_brains_db.md#line-97---get_structures_hierarchy)
  * [line: 132 - `get_structures_reconstructions`](insects_brains_db.md#line-132---get_structures_reconstructions)
  * [line: 216 - `get_brain`](insects_brains_db.md#line-216---get_brain)
  * [line: 245 - `download_and_write_mesh`](insects_brains_db.md#line-245---download_and_write_mesh)
  * [line: 262 - `make_root_mesh`](insects_brains_db.md#line-262---make_root_mesh)
  * [line: 281 - `_get_structure_mesh`](insects_brains_db.md#line-281---_get_structure_mesh)
  * [line: 315 - `_check_valid_region_arg`](insects_brains_db.md#line-315---_check_valid_region_arg)
  * [line: 326 - `_check_obj_file`](insects_brains_db.md#line-326---_check_obj_file)
  * [line: 339 - `get_region_color`](insects_brains_db.md#line-339---get_region_color)
  * [line: 368 - `get_brain_regions`](insects_brains_db.md#line-368---get_brain_regions)
  * [line: 98 - `add_descendants_to_tree`](insects_brains_db.md#line-98---add_descendants_to_tree)

## **IBDB**

### line: 55 - `__init__`

```text
def __init__(self, species=None, sex=None, base_dir=None, make_root=True, **kwargs):
```

> no docstring

### line: 80 - `get_brain_id_from_species_name`

```text
def get_brain_id_from_species_name(self, sel_species):
```

> no docstring

### line: 97 - `get_structures_hierarchy`

```text
def get_structures_hierarchy(self):
```

> no docstring

### line: 132 - `get_structures_reconstructions`

```text
def get_structures_reconstructions(self, species, sex):
```

> no docstring

### line: 216 - `get_brain`

```text
def get_brain(self, species=None, sex=None):
```

> no docstring

### line: 245 - `download_and_write_mesh`

```text
def download_and_write_mesh(self, acronym, obj_path):
```

> no docstring

### line: 262 - `make_root_mesh`

```text
def make_root_mesh(self):
```

> no docstring

### line: 281 - `_get_structure_mesh`

```text
def _get_structure_mesh(self, acronym, **kwargs):
```

> Fetches the mesh for a brain region from the atlas.  
> :param acronym: string, acronym of brain region  
> :param \*\*kwargs:

### line: 315 - `_check_valid_region_arg`

```text
def _check_valid_region_arg(self, region):
```

> Check that the string passed is a valid brain region name.

### line: 326 - `_check_obj_file`

```text
def _check_obj_file(self, region, obj_file):
```

> If the .obj file for a brain region hasn't been downloaded already, this function downloads it and writes it.  
> :param region: string, acronym of brain region  
> :param obj\_file: path to .obj file to write downloaded data.

### line: 339 - `get_region_color`

```text
def get_region_color(self, regions):
```

> Gets the RGB color of a brain region from the atlas.  
> :param regions: list of regions acronyms.

### line: 368 - `get_brain_regions`

```text
def get_brain_regions(self, brain_regions, alpha=None, colors=None, use_original_color=True, **kwargs):
```

> no docstring

### line: 98 - `add_descendants_to_tree`

```text
def add_descendants_to_tree(tree, structure, parent_id=None):
```

> Recursively goes through all the the descendants of a region and adds them to the tree

