# VolumetricConnectomeAPI

## Contents

* [**VolumetricAPI**](volumetricconnectomeapi.md#volumetricapi)
  * [line: 47 - `__init__`](volumetricconnectomeapi.md#line-47---__init__)
  * [line: 110 - `__getattr__`](volumetricconnectomeapi.md#line-110---__getattr__)
  * [line: 124 - `_get_structure_id`](volumetricconnectomeapi.md#line-124---_get_structure_id)
  * [line: 133 - `_load_voxel_data`](volumetricconnectomeapi.md#line-133---_load_voxel_data)
  * [line: 170 - `_get_coordinates_from_voxel_id`](volumetricconnectomeapi.md#line-170---_get_coordinates_from_voxel_id)
  * [line: 186 - `_get_mask_coords`](volumetricconnectomeapi.md#line-186---_get_mask_coords)
  * [line: 201 - `_get_voxel_id_from_coordinates`](volumetricconnectomeapi.md#line-201---_get_voxel_id_from_coordinates)
  * [line: 223 - `_get_cache_filename`](volumetricconnectomeapi.md#line-223---_get_cache_filename)
  * [line: 242 - `_get_from_cache`](volumetricconnectomeapi.md#line-242---_get_from_cache)
  * [line: 253 - `save_to_cache`](volumetricconnectomeapi.md#line-253---save_to_cache)
  * [line: 264 - `get_source`](volumetricconnectomeapi.md#line-264---get_source)
  * [line: 286 - `get_target_mask`](volumetricconnectomeapi.md#line-286---get_target_mask)
  * [line: 297 - `get_target`](volumetricconnectomeapi.md#line-297---get_target)
  * [line: 327 - `get_projection`](volumetricconnectomeapi.md#line-327---get_projection)
  * [line: 400 - `get_mapped_projection`](volumetricconnectomeapi.md#line-400---get_mapped_projection)
  * [line: 416 - `get_mapped_projection_to_point`](volumetricconnectomeapi.md#line-416---get_mapped_projection_to_point)
  * [line: 452 - `get_mapped_projection_from_point`](volumetricconnectomeapi.md#line-452---get_mapped_projection_from_point)
  * [line: 497 - `add_mapped_projection`](volumetricconnectomeapi.md#line-497---add_mapped_projection)
  * [line: 551 - `add_mapped_projection_to_point`](volumetricconnectomeapi.md#line-551---add_mapped_projection_to_point)
  * [line: 625 - `add_mapped_projection_from_point`](volumetricconnectomeapi.md#line-625---add_mapped_projection_from_point)
  * [line: 630 - `add_volume`](volumetricconnectomeapi.md#line-630---add_volume)

## **VolumetricAPI**

```text
This class takes care of downloading, analysing and rendering data from:
"High-resolution data-driven model of the mouse connectome ", Knox et al 2018.
[https://www.mitpressjournals.org/doi/full/10.1162/netn_a_00066].

These data can be used to look at spatialised projection strength with sub-region (100um) resolution.
e.g. to look at where in region B are the projections from region A, you can use this class.

To download the data, this class uses code from: https://github.com/AllenInstitute/mouse_connectivity_models.
```

### line: 47 - `__init__`

```text
def __init__(self, base_dir=None, add_root=True, use_cache=True, scene_kwargs={}, **kwargs):
```

> Initialise the class instance to get a few useful paths and variables.  
> :param base\_dir: str, path to base directory in which all of brainrender data are stored. Pass only if you want to use a different one from what's default.  
> :param add\_root: bool, if True the root mesh is added to the rendered scene  
> :param use\_cache: if true data are loaded from a cache to speed things up. Useful to set it to false to help debugging.  
> :param scene\_kwargs: dict, params passed to the instance of Scene associated with this class

### line: 110 - `__getattr__`

```text
def __getattr__(self, attr):
```

> no docstring

### line: 124 - `_get_structure_id`

```text
def _get_structure_id(self, struct):
```

> Get the ID of a structure \(or list of structures\) given it's acronym

### line: 133 - `_load_voxel_data`

```text
def _load_voxel_data(self):
```

> Load the VoxelData array from Knox et al 2018

### line: 170 - `_get_coordinates_from_voxel_id`

```text
def _get_coordinates_from_voxel_id(self, p0, as_source=True):
```

> Takes the index of a voxel and returns the 3D coordinates in reference space. The index number should be extracted with either a source\_mask or a target\_mask.If target\_mask wa used set as\_source as False.  
> :param p0: int

### line: 186 - `_get_mask_coords`

```text
def _get_mask_coords(self, as_source):
```

> no docstring

### line: 201 - `_get_voxel_id_from_coordinates`

```text
def _get_voxel_id_from_coordinates(self, p0, as_source=True):
```

> no docstring

### line: 223 - `_get_cache_filename`

```text
def _get_cache_filename(self, tgt, what):
```

> Data are cached according to a naming convention, this function gets the name for an objectaccording to the convention

### line: 242 - `_get_from_cache`

```text
def _get_from_cache(self, tgt, what):
```

> tries to load objects from cached data, if they exist

### line: 253 - `save_to_cache`

```text
def save_to_cache(self, tgt, what, obj):
```

> Saves data to cache to avoid loading thema again in the future

### line: 264 - `get_source`

```text
def get_source(self, source, hemisphere='both'):
```

> Loads the mask for a source structure  
> :param source: str or list of str with acronym of source regions  
> :param hemisphere: str, \['both', 'left', 'right'\]. Which hemisphere to consider.

### line: 286 - `get_target_mask`

```text
def get_target_mask(self, target, hemisphere):
```

> returns a 'key' array and a mask objectused to transform projection data from linear arrays to 3D volumes.

### line: 297 - `get_target`

```text
def get_target(self, target, hemisphere='both'):
```

> Loads the mask for a target structure.  
> :param target: str or list of str with acronym of target regions  
> :param hemisphere: str, \['both', 'left', 'right'\]. Which hemisphere to consider.

### line: 327 - `get_projection`

```text
def get_projection(self, source, target, name, hemisphere='both', projection_mode='mean', mode='target'):
```

> Gets the spatialised projection intensity from a source to a target.  
> :param source: str or list of str with acronym of source regions  
> :param target: str or list of str with acronym of target regions  
> :param name: str, name of the projection  
> :param projection\_mode: str, if 'mean' the data from different experiments are averaged, if 'max' the highest value is taken.  
> :param mode: str. If 'target' the spatialised projection strength in the target structures is returned, usefule to see where source projects to in target. Otherwise if 'source' the spatialised projection strength in the source structure is return. Useful to see which part of source projects to target.:return: 1D numpy array with mean projection from source to target voxels

### line: 400 - `get_mapped_projection`

```text
def get_mapped_projection(self, source, target, name, **kwargs):
```

> Gets the spatialised projection intensity from a source to a target, but as a mapped volume instead of a linear array.  
> :param source: str or list of str with acronym of source regions  
> :param target: str or list of str with acronym of target regions  
> :param name: str, name of the projection:return: 3D numpy array with projectino intensity

### line: 416 - `get_mapped_projection_to_point`

```text
def get_mapped_projection_to_point(self, p0, restrict_to=None, restrict_to_hemisphere='both'):
```

> Gets projection intensity from all voxels to the voxel corresponding to a point of interest

### line: 452 - `get_mapped_projection_from_point`

```text
def get_mapped_projection_from_point(self, p0, restrict_to=None, restrict_to_hemisphere='both'):
```

> Gets projection intensity from all voxels to the voxel corresponding to a point of interest

### line: 497 - `add_mapped_projection`

```text
def add_mapped_projection(self, source, target, actor_kwargs={}, render_source_region=False, render_target_region=False, regions_kwargs={}, **kwargs):
```

> Gets the spatialised projection intensity from a source to a targetand renders it as a vedo lego visualisation.  
> :param source: str or list of str with acronym of source regions  
> :param target: str or list of str with acronym of target regions  
> :param render\_source\_region: bool, if true a wireframe mesh of source regions is rendered  
> :param render\_target\_region: bool, if true a wireframe mesh of target regions is rendered  
> :param regions\_kwargs: pass options to specify how brain regions should look like  
> :param kwargs: kwargs can be used to control how the rendered object looks like. Look at the arguments of 'add\_volume' to see what arguments are available.

### line: 551 - `add_mapped_projection_to_point`

```text
def add_mapped_projection_to_point(self, p0, show_point=True, show_point_region=False, show_crosshair=True, crosshair_kwargs={}, point_region_kwargs={}, point_kwargs={}, from_point=False, **kwargs):
```

> no docstring

### line: 625 - `add_mapped_projection_from_point`

```text
def add_mapped_projection_from_point(self, *args, **kwargs):
```

> no docstring

### line: 630 - `add_volume`

```text
def add_volume(self, volume, cmap='afmhot_r', alpha=1, add_colorbar=True, **kwargs):
```

> Renders intensitdata from a 3D numpy array as a lego volumetric actor.  
> :param volume: np 3D array with number of dimensions = those of the 100um reference space.  
> :param cmap: str with name of colormap to use  
> :param alpha: float, transparency  
> :param add\_colorbar: if True a colorbar is added to show the values of the colormap

