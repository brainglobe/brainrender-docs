



Contents
========

* [**VolumetricAPI**](#volumetricapi)
	* [**`__init__`** [#47]](#__init__-47)
	* [**`__getattr__`** [#111]](#__getattr__-111)
	* [**`_get_structure_id`** [#125]](#_get_structure_id-125)
	* [**`_load_voxel_data`** [#134]](#_load_voxel_data-134)
	* [**`_get_coordinates_from_voxel_id`** [#171]](#_get_coordinates_from_voxel_id-171)
	* [**`_get_mask_coords`** [#187]](#_get_mask_coords-187)
	* [**`_get_voxel_id_from_coordinates`** [#202]](#_get_voxel_id_from_coordinates-202)
	* [**`_get_cache_filename`** [#224]](#_get_cache_filename-224)
	* [**`_get_from_cache`** [#243]](#_get_from_cache-243)
	* [**`save_to_cache`** [#254]](#save_to_cache-254)
	* [**`get_source`** [#265]](#get_source-265)
	* [**`get_target_mask`** [#287]](#get_target_mask-287)
	* [**`get_target`** [#298]](#get_target-298)
	* [**`get_projection`** [#328]](#get_projection-328)
	* [**`get_mapped_projection`** [#401]](#get_mapped_projection-401)
	* [**`get_mapped_projection_to_point`** [#417]](#get_mapped_projection_to_point-417)
	* [**`get_mapped_projection_from_point`** [#453]](#get_mapped_projection_from_point-453)
	* [**`add_mapped_projection`** [#498]](#add_mapped_projection-498)
	* [**`add_mapped_projection_to_point`** [#552]](#add_mapped_projection_to_point-552)
	* [**`add_mapped_projection_from_point`** [#626]](#add_mapped_projection_from_point-626)
	* [**`add_volume`** [#631]](#add_volume-631)


&nbsp;

--------
# **VolumetricAPI**


```
This class takes care of downloading, analysing and rendering data from:
"High-resolution data-driven model of the mouse connectome ", Knox et al 2018.
[https://www.mitpressjournals.org/doi/full/10.1162/netn_a_00066].

These data can be used to look at spatialised projection strength with sub-region (100um) resolution.
e.g. to look at where in region B are the projections from region A, you can use this class.

To download the data, this class uses code from: https://github.com/AllenInstitute/mouse_connectivity_models.
```

&nbsp;
## **`__init__`** [#47]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/volumetric/VolumetricConnectomeAPI.py#L47) online

```python
def __init__(self, base_dir=None, add_root=True, use_cache=True,
    scene_kwargs={}, **kwargs):
```

&nbsp;  
docstring:

```text
Initialise the class instance to get a few useful paths and variables.

:param base_dir: str, path to base directory in which all of
    brainrender data are stored.

Pass only if you want to use a different one from what's default.

:param add_root: bool, if True the root mesh is added to the rendered
    scene

:param use_cache: if true data are loaded from a cache to speed things
    up.

Useful to set it to false to help debugging.

:param scene_kwargs: dict, params passed to the instance of Scene
    associated with this class

```

&nbsp;
## **`__getattr__`** [#111]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/volumetric/VolumetricConnectomeAPI.py#L111) online

```python
def __getattr__(self, attr):
```

&nbsp;  
docstring:

no docstring

&nbsp;
## **`_get_structure_id`** [#125]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/volumetric/VolumetricConnectomeAPI.py#L125) online

```python
def _get_structure_id(self, struct):
```

&nbsp;  
docstring:

```text
Get the ID of a structure (or list of structures) given it's acronym

```

&nbsp;
## **`_load_voxel_data`** [#134]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/volumetric/VolumetricConnectomeAPI.py#L134) online

```python
def _load_voxel_data(self):
```

&nbsp;  
docstring:

```text
Load the VoxelData array from Knox et al 2018

```

&nbsp;
## **`_get_coordinates_from_voxel_id`** [#171]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/volumetric/VolumetricConnectomeAPI.py#L171) online

```python
def _get_coordinates_from_voxel_id(self, p0, as_source=True):
```

&nbsp;  
docstring:

```text
Takes the index of a voxel and returns the 3D coordinates in reference
    space.

The index number should be extracted with either a source_mask or a
    target_mask.

If target_mask wa used set as_source as False.

:param p0: int

```

&nbsp;
## **`_get_mask_coords`** [#187]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/volumetric/VolumetricConnectomeAPI.py#L187) online

```python
def _get_mask_coords(self, as_source):
```

&nbsp;  
docstring:

no docstring

&nbsp;
## **`_get_voxel_id_from_coordinates`** [#202]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/volumetric/VolumetricConnectomeAPI.py#L202) online

```python
def _get_voxel_id_from_coordinates(self, p0, as_source=True):
```

&nbsp;  
docstring:

no docstring

&nbsp;
## **`_get_cache_filename`** [#224]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/volumetric/VolumetricConnectomeAPI.py#L224) online

```python
def _get_cache_filename(self, tgt, what):
```

&nbsp;  
docstring:

```text
Data are cached according to a naming convention, this function gets
    the name for an object

according to the convention

```

&nbsp;
## **`_get_from_cache`** [#243]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/volumetric/VolumetricConnectomeAPI.py#L243) online

```python
def _get_from_cache(self, tgt, what):
```

&nbsp;  
docstring:

```text
tries to load objects from cached data, if they exist

```

&nbsp;
## **`save_to_cache`** [#254]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/volumetric/VolumetricConnectomeAPI.py#L254) online

```python
def save_to_cache(self, tgt, what, obj):
```

&nbsp;  
docstring:

```text
Saves data to cache to avoid loading thema again in the future

```

&nbsp;
## **`get_source`** [#265]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/volumetric/VolumetricConnectomeAPI.py#L265) online

```python
def get_source(self, source, hemisphere='both'):
```

&nbsp;  
docstring:

```text
Loads the mask for a source structure

:param source: str or list of str with acronym of source regions

:param hemisphere: str, ['both', 'left', 'right']. Which hemisphere to
    consider.

```

&nbsp;
## **`get_target_mask`** [#287]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/volumetric/VolumetricConnectomeAPI.py#L287) online

```python
def get_target_mask(self, target, hemisphere):
```

&nbsp;  
docstring:

```text
returns a 'key' array and a mask object

used to transform projection data from linear arrays to 3D volumes.

```

&nbsp;
## **`get_target`** [#298]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/volumetric/VolumetricConnectomeAPI.py#L298) online

```python
def get_target(self, target, hemisphere='both'):
```

&nbsp;  
docstring:

```text
Loads the mask for a target structure.

:param target: str or list of str with acronym of target regions

:param hemisphere: str, ['both', 'left', 'right']. Which hemisphere to
    consider.

```

&nbsp;
## **`get_projection`** [#328]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/volumetric/VolumetricConnectomeAPI.py#L328) online

```python
def get_projection(self, source, target, name, hemisphere='both',
    projection_mode='mean', mode='target'):
```

&nbsp;  
docstring:

```text
Gets the spatialised projection intensity from a source to a target.

:param source: str or list of str with acronym of source regions

:param target: str or list of str with acronym of target regions

:param name: str, name of the projection

:param projection_mode: str, if 'mean' the data from different
    experiments are averaged,

if 'max' the highest value is taken.

:param mode: str. If 'target' the spatialised projection strength in
    the target structures is returned, usefule

to see where source projects to in target. Otherwise if 'source' the
    spatialised projection strength in

the source structure is return. Useful to see which part of source
    projects to target.

:return: 1D numpy array with mean projection from source to target
    voxels

```

&nbsp;
## **`get_mapped_projection`** [#401]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/volumetric/VolumetricConnectomeAPI.py#L401) online

```python
def get_mapped_projection(self, source, target, name, **kwargs):
```

&nbsp;  
docstring:

```text
Gets the spatialised projection intensity from a source to a target,
    but as

a mapped volume instead of a linear array.

:param source: str or list of str with acronym of source regions

:param target: str or list of str with acronym of target regions

:param name: str, name of the projection

:return: 3D numpy array with projectino intensity

```

&nbsp;
## **`get_mapped_projection_to_point`** [#417]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/volumetric/VolumetricConnectomeAPI.py#L417) online

```python
def get_mapped_projection_to_point(self, p0, restrict_to=None,
    restrict_to_hemisphere='both'):
```

&nbsp;  
docstring:

```text
Gets projection intensity from all voxels to the voxel corresponding
    to a point of interest

```

&nbsp;
## **`get_mapped_projection_from_point`** [#453]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/volumetric/VolumetricConnectomeAPI.py#L453) online

```python
def get_mapped_projection_from_point(self, p0, restrict_to=None,
    restrict_to_hemisphere='both'):
```

&nbsp;  
docstring:

```text
Gets projection intensity from all voxels to the voxel corresponding
    to a point of interest

```

&nbsp;
## **`add_mapped_projection`** [#498]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/volumetric/VolumetricConnectomeAPI.py#L498) online

```python
def add_mapped_projection(self, source, target, actor_kwargs={},
    render_source_region=False, render_target_region=False,
    regions_kwargs={}, **kwargs):
```

&nbsp;  
docstring:

```text
Gets the spatialised projection intensity from a source to a target

and renders it as a vedo lego visualisation.

:param source: str or list of str with acronym of source regions

:param target: str or list of str with acronym of target regions

:param render_source_region: bool, if true a wireframe mesh of source
    regions is rendered

:param render_target_region: bool, if true a wireframe mesh of target
    regions is rendered

:param regions_kwargs: pass options to specify how brain regions
    should look like

:param kwargs: kwargs can be used to control how the rendered object
    looks like.

Look at the arguments of 'add_volume' to see what arguments are
    available.

```

&nbsp;
## **`add_mapped_projection_to_point`** [#552]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/volumetric/VolumetricConnectomeAPI.py#L552) online

```python
def add_mapped_projection_to_point(self, p0, show_point=True,
    show_point_region=False, show_crosshair=True, crosshair_kwargs={},
    point_region_kwargs={}, point_kwargs={}, from_point=False, **kwargs):
```

&nbsp;  
docstring:

no docstring

&nbsp;
## **`add_mapped_projection_from_point`** [#626]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/volumetric/VolumetricConnectomeAPI.py#L626) online

```python
def add_mapped_projection_from_point(self, *args, **kwargs):
```

&nbsp;  
docstring:

no docstring

&nbsp;
## **`add_volume`** [#631]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/volumetric/VolumetricConnectomeAPI.py#L631) online

```python
def add_volume(self, volume, cmap='afmhot_r', alpha=1,
    add_colorbar=True, **kwargs):
```

&nbsp;  
docstring:

```text
Renders intensitdata from a 3D numpy array as a lego volumetric actor.

:param volume: np 3D array with number of dimensions = those of the
    100um reference space.

:param cmap: str with name of colormap to use

:param alpha: float, transparency

:param add_colorbar: if True a colorbar is added to show the values of
    the colormap

```