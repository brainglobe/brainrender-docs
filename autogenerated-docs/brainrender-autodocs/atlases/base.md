# base

## Contents

* [**Base**](base.md#base)
  * [**`__init__`** \[\#18\]](base.md#__init__-18)
  * [**`get_plane_at_point`** \[\#26\]](base.md#get_plane_at_point-26)
  * [**`get_sagittal_plane`** \[\#42\]](base.md#get_sagittal_plane-42)
  * [**`get_horizontal_plane`** \[\#69\]](base.md#get_horizontal_plane-69)
  * [**`get_coronal_plane`** \[\#96\]](base.md#get_coronal_plane-96)
  * [**`get_region_CenterOfMass`** \[\#124\]](base.md#get_region_centerofmass-124)
  * [**`_get_structure_mesh`** \[\#167\]](base.md#_get_structure_mesh-167)
  * [**`get_brain_regions`** \[\#171\]](base.md#get_brain_regions-171)
  * [**`get_structure_ancestors`** \[\#286\]](base.md#get_structure_ancestors-286)
  * [**`get_structure_descendants`** \[\#328\]](base.md#get_structure_descendants-328)
  * [**`get_structure_parent`** \[\#333\]](base.md#get_structure_parent-333)
  * [**`get_region_unilateral`** \[\#359\]](base.md#get_region_unilateral-359)
  * [**`mirror_point_across_hemispheres`** \[\#398\]](base.md#mirror_point_across_hemispheres-398)
  * [**`get_colors_from_coordinates`** \[\#403\]](base.md#get_colors_from_coordinates-403)

## **Base**

### **`__init__`** \[\#18\]

Check the [_**`source code`**_](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/atlases/base.py#L18) online

```python
def __init__(self):
```

   
docstring:

no docstring

### **`get_plane_at_point`** \[\#26\]

Check the [_**`source code`**_](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/atlases/base.py#L26) online

```python
def get_plane_at_point(self, pos, norm, sx, sy, color='lightgray',
    alpha=0.25, **kwargs):
```

   
docstring:

```text
Returns a plane going through a point at pos, oriented

orthogonally to the vector norm and of width and height

sx, sy.

:param pos: 3-tuple or list with x,y,z, coords of point the plane goes
    through

:param sx, sy: int, width and height of the plane

:param norm: 3-tuple or list with 3d vector the plane is orthogonal to

:param color, alpha: plane color and transparency
```

### **`get_sagittal_plane`** \[\#42\]

Check the [_**`source code`**_](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/atlases/base.py#L42) online

```python
def get_sagittal_plane(self, pos=None, **kwargs):
```

   
docstring:

```text
Creates a Plane actor centered at the midpoint of root (or a user
    given locatin)

and oriented along the sagittal axis

:param pos: if not None, passe a list of 3 xyz defining the position
    of the

point the plane goes through.
```

### **`get_horizontal_plane`** \[\#69\]

Check the [_**`source code`**_](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/atlases/base.py#L69) online

```python
def get_horizontal_plane(self, pos=None, **kwargs):
```

   
docstring:

```text
Creates a Plane actor centered at the midpoint of root (or a user
    given locatin)

and oriented along the horizontal axis

:param pos: if not None, passe a list of 3 xyz defining the position
    of the

point the plane goes through.
```

### **`get_coronal_plane`** \[\#96\]

Check the [_**`source code`**_](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/atlases/base.py#L96) online

```python
def get_coronal_plane(self, pos=None, **kwargs):
```

   
docstring:

```text
Creates a Plane actor centered at the midpoint of root (or a user
    given locatin)

and oriented along the coronal axis

:param pos: if not None, passe a list of 3 xyz defining the position
    of the

point the plane goes through.
```

### **`get_region_CenterOfMass`** \[\#124\]

Check the [_**`source code`**_](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/atlases/base.py#L124) online

```python
def get_region_CenterOfMass(self, regions, unilateral=True,
    hemisphere='right'):
```

   
docstring:

```text
Get the center of mass of the 3d mesh of one or multiple brain
    regions.

:param regions: str, list of brain regions acronyms

:param unilateral: bool, if True, the CoM is relative to one
    hemisphere (Default value = True)

:param hemisphere: str, if unilteral=True, specifies which hemisphere
    to use ['left' or 'right'] (Default value = "right")

:returns: coms = {list, dict} -- [if only one regions is passed, then
    just returns the CoM coordinates for that region.

If a list is passed then a dictionary is returned. ]
```

### **`_get_structure_mesh`** \[\#167\]

Check the [_**`source code`**_](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/atlases/base.py#L167) online

```python
def _get_structure_mesh(self, acronym, **kwargs):
```

   
docstring:

no docstring

### **`get_brain_regions`** \[\#171\]

Check the [_**`source code`**_](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/atlases/base.py#L171) online

```python
def get_brain_regions(self, brain_regions, add_labels=False,
    colors=None, use_original_color=True, alpha=None, hemisphere=None,
    verbose=False, **kwargs):
```

   
docstring:

```text
Gets brain regions meshes for rendering

Many parameters can be passed to specify how the regions should be
    rendered.

To treat a subset of the rendered regions, specify which regions are
    VIP.

Use the kwargs to specify more detailes on how the regins should be
    rendered (e.g. wireframe look)

:param brain_regions: str list of acronyms of brain regions

:param colors: str, color of rendered brian regions (Default value =
    None)

:param use_original_color: bool, if True, the allen's default color
    for the region is used.  (Default value = False)

:param alpha: float, transparency of the rendered brain regions
    (Default value = None)

:param hemisphere: str (Default value = None)

:param add_labels: bool (default False). If true a label is added to
    each regions' actor. The label is visible when hovering the mouse over
    the actor

:param **kwargs: used to determine a bunch of thigs, including the
    look and location of lables from scene.add_labels
```

### **`get_structure_ancestors`** \[\#286\]

Check the [_**`source code`**_](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/atlases/base.py#L286) online

```python
def get_structure_ancestors(self, regions, ancestors=True,
    descendants=False):
```

   
docstring:

```text
Get's the ancestors of the region(s) passed as arguments

:param regions: str, list of str with acronums of regions of interest

:param ancestors: if True, returns the ancestors of the region
    (Default value = True)

:param descendants: if True, returns the descendants of the region
    (Default value = False)
```

### **`get_structure_descendants`** \[\#328\]

Check the [_**`source code`**_](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/atlases/base.py#L328) online

```python
def get_structure_descendants(self, regions):
```

   
docstring:

no docstring

### **`get_structure_parent`** \[\#333\]

Check the [_**`source code`**_](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/atlases/base.py#L333) online

```python
def get_structure_parent(self, acronyms):
```

   
docstring:

```text
Gets the parent of a brain region (or list of regions) from the
    hierarchical structure of the

Allen Brain Atals.

:param acronyms: list of acronyms of brain regions.
```

### **`get_region_unilateral`** \[\#359\]

Check the [_**`source code`**_](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/atlases/base.py#L359) online

```python
def get_region_unilateral(self, region, hemisphere='both', color=None,
    alpha=None):
```

   
docstring:

```text
Regions meshes are loaded with both hemispheres' meshes by default.

This function splits them in two.

:param region: str, actors of brain region

:param hemisphere: str, which hemisphere to return ['left', 'right' or
    'both'] (Default value = "both")

:param color: color of each side's mesh. (Default value = None)

:param alpha: transparency of each side's mesh.  (Default value =
    None)
```

### **`mirror_point_across_hemispheres`** \[\#398\]

Check the [_**`source code`**_](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/atlases/base.py#L398) online

```python
def mirror_point_across_hemispheres(self, point):
```

   
docstring:

no docstring

### **`get_colors_from_coordinates`** \[\#403\]

Check the [_**`source code`**_](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/atlases/base.py#L403) online

```python
def get_colors_from_coordinates(self, p0):
```

   
docstring:

```text
Given a point or a list of points returns a list of colors where

each item is the color of the brain region each point is in
```

