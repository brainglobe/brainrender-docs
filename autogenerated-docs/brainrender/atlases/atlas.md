



Contents
========

* [**Atlas**](#atlas)
	* [**`__init__`** [#26]](#__init__-26)
	* [**`get_plane_at_point`** [#46]](#get_plane_at_point-46)
	* [**`get_region_CenterOfMass`** [#101]](#get_region_centerofmass-101)
	* [**`_get_structure_mesh`** [#144]](#_get_structure_mesh-144)
	* [**`get_brain_regions`** [#148]](#get_brain_regions-148)
	* [**`get_neurons`** [#257]](#get_neurons-257)
	* [**`get_region_unilateral`** [#391]](#get_region_unilateral-391)
	* [**`mirror_point_across_hemispheres`** [#430]](#mirror_point_across_hemispheres-430)
	* [**`get_colors_from_coordinates`** [#435]](#get_colors_from_coordinates-435)


&nbsp;

--------
# **Atlas**




&nbsp;
## **`__init__`** [#26]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/atlases/atlas.py#L26) online

```python
def __init__(self, atlas_name, *args, base_dir=None, **kwargs):
```

&nbsp;  
docstring:

no docstring

&nbsp;
## **`get_plane_at_point`** [#46]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/atlases/atlas.py#L46) online

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
## **`get_region_CenterOfMass`** [#101]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/atlases/atlas.py#L101) online

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
## **`_get_structure_mesh`** [#144]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/atlases/atlas.py#L144) online

```python
def _get_structure_mesh(self, acronym, **kwargs):
```

&nbsp;  
docstring:

no docstring

&nbsp;
## **`get_brain_regions`** [#148]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/atlases/atlas.py#L148) online

```python
def get_brain_regions(self, *brain_regions, add_labels=False,
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
## **`get_neurons`** [#257]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/atlases/atlas.py#L257) online

```python
def get_neurons(self, neurons, color=None, display_axon=True,
    display_dendrites=True, alpha=1, neurite_radius=None,
    soma_radius=None, use_cache=True):
```

&nbsp;  
docstring:

```text
Gets rendered morphological data of neurons reconstructions

Accepts neurons argument as:

- file(s) with morphological data

- vedo mesh actor(s) of entire neurons reconstructions

- dictionary or list of dictionary with actors for different neuron
    parts

:param neurons: str, list, dict. File(s) with neurons data or list of
    rendered neurons.

:param display_axon, display_dendrites: if set to False the
    corresponding neurite is not rendered

:param color: default None. Can be:

- None: each neuron is given a random color

- color: rbg, hex etc. If a single color is passed all neurons will
    have that color

- cmap: str with name of a colormap: neurons are colored based on
    their sequential order and cmap

- dict: a dictionary specifying a color for soma, dendrites and axon
    actors, will be the same for all neurons

- list: a list of length = number of neurons with either a single
    color for each neuron

or a dictionary of colors for each neuron

:param alpha: float in range 0,1. Neurons transparency

:param neurite_radius: float > 0 , radius of tube actor representing
    neurites

:param use_cache: bool, if True a cache is used to avoid having to
    crate a neuron's mesh anew, otherwise a new mesh is created

```

&nbsp;
## **`get_region_unilateral`** [#391]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/atlases/atlas.py#L391) online

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
## **`mirror_point_across_hemispheres`** [#430]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/atlases/atlas.py#L430) online

```python
def mirror_point_across_hemispheres(self, point):
```

&nbsp;  
docstring:

no docstring

&nbsp;
## **`get_colors_from_coordinates`** [#435]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/atlases/atlas.py#L435) online

```python
def get_colors_from_coordinates(self, p0):
```

&nbsp;  
docstring:

```text
Given a point or a list of points returns a list of colors where

each item is the color of the brain region each point is in

```