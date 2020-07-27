



Contents
========

* [**Atlas**](#atlas)
	* [**`__init__`** [#20]](#__init__-20)
	* [**`get_plane_at_point`** [#39]](#get_plane_at_point-39)
	* [**`get_region_CenterOfMass`** [#89]](#get_region_centerofmass-89)
	* [**`_get_structure_mesh`** [#132]](#_get_structure_mesh-132)
	* [**`get_brain_regions`** [#136]](#get_brain_regions-136)
	* [**`get_region_unilateral`** [#249]](#get_region_unilateral-249)
	* [**`mirror_point_across_hemispheres`** [#288]](#mirror_point_across_hemispheres-288)
	* [**`get_colors_from_coordinates`** [#293]](#get_colors_from_coordinates-293)


&nbsp;

--------
# **Atlas**




&nbsp;
## **`__init__`** [#20]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/atlases/atlas.py#L20) online

```python
def __init__(self, atlas_name, *args, base_dir=None, **kwargs):
```

&nbsp;  
docstring:

no docstring

&nbsp;
## **`get_plane_at_point`** [#39]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/atlases/atlas.py#L39) online

```python
def get_plane_at_point(self, pos=None, norm=None, plane=None, sx=None,
    sy=None, color='lightgray', alpha=0.25, **kwargs):
```

&nbsp;  
docstring:

```text
Returns a plane going through a point at pos, oriented

orthogonally to the vector norm and of width and height

sx, sy.

:param pos: 3-tuple or list with x,y,z, coords of point the plane goes
    through

:param norm: 3-tuple with plane's normal vector (optional)

:param sx, sy: int, width and height of the plane

:param plane: "sagittal", "horizontal", or "frontal"

:param color, alpha: plane color and transparency

```

&nbsp;
## **`get_region_CenterOfMass`** [#89]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/atlases/atlas.py#L89) online

```python
def get_region_CenterOfMass(self, regions, unilateral=True,
    hemisphere='right'):
```

&nbsp;  
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

&nbsp;
## **`_get_structure_mesh`** [#132]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/atlases/atlas.py#L132) online

```python
def _get_structure_mesh(self, acronym, **kwargs):
```

&nbsp;  
docstring:

no docstring

&nbsp;
## **`get_brain_regions`** [#136]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/atlases/atlas.py#L136) online

```python
def get_brain_regions(self, brain_regions, add_labels=False,
    colors=None, use_original_color=True, alpha=None, hemisphere=None,
    verbose=False, **kwargs):
```

&nbsp;  
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

&nbsp;
## **`get_region_unilateral`** [#249]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/atlases/atlas.py#L249) online

```python
def get_region_unilateral(self, region, hemisphere='both', color=None,
    alpha=None):
```

&nbsp;  
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

&nbsp;
## **`mirror_point_across_hemispheres`** [#288]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/atlases/atlas.py#L288) online

```python
def mirror_point_across_hemispheres(self, point):
```

&nbsp;  
docstring:

no docstring

&nbsp;
## **`get_colors_from_coordinates`** [#293]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/atlases/atlas.py#L293) online

```python
def get_colors_from_coordinates(self, p0):
```

&nbsp;  
docstring:

```text
Given a point or a list of points returns a list of colors where

each item is the color of the brain region each point is in

```