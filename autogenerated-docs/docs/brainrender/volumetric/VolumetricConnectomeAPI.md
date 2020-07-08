



Contents
========

* [**VolumetricAPI**](#volumetricapi)
	* [**`__init__`** [#47]](#__init__-47)
	* [**`__getattr__`** [#110]](#__getattr__-110)
	* [**`_get_structure_id`** [#124]](#_get_structure_id-124)
	* [**`_load_voxel_data`** [#133]](#_load_voxel_data-133)
	* [**`_get_coordinates_from_voxel_id`** [#170]](#_get_coordinates_from_voxel_id-170)
	* [**`_get_mask_coords`** [#186]](#_get_mask_coords-186)
	* [**`_get_voxel_id_from_coordinates`** [#201]](#_get_voxel_id_from_coordinates-201)
	* [**`_get_cache_filename`** [#223]](#_get_cache_filename-223)
	* [**`_get_from_cache`** [#242]](#_get_from_cache-242)
	* [**`save_to_cache`** [#253]](#save_to_cache-253)
	* [**`get_source`** [#264]](#get_source-264)
	* [**`get_target_mask`** [#286]](#get_target_mask-286)
	* [**`get_target`** [#297]](#get_target-297)
	* [**`get_projection`** [#327]](#get_projection-327)
	* [**`get_mapped_projection`** [#400]](#get_mapped_projection-400)
	* [**`get_mapped_projection_to_point`** [#416]](#get_mapped_projection_to_point-416)
	* [**`get_mapped_projection_from_point`** [#452]](#get_mapped_projection_from_point-452)
	* [**`add_mapped_projection`** [#497]](#add_mapped_projection-497)
	* [**`add_mapped_projection_to_point`** [#551]](#add_mapped_projection_to_point-551)
	* [**`add_mapped_projection_from_point`** [#625]](#add_mapped_projection_from_point-625)
	* [**`add_volume`** [#630]](#add_volume-630)


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
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/volumetric/VolumetricConnectomeAPI.py#L47) online

```python
def __init__(self, base_dir=None, add_root=True, use_cache=True, scene_kwargs={}, **kwargs):
```  


```text
Initialise the class instance to get a few useful paths and
variables.
:param base_dir: str, path to base directory in which all of
brainrender data are stored.
pass only if you want to use a different one from what's
default.
:param add_root: bool, if true the root mesh is added to the
rendered scene
:param use_cache: if true data are loaded from a cache to
speed things up.
useful to set it to false to help debugging.
:param scene_kwargs: dict, params passed to the instance of
scene associated with this class
```

&nbsp;
## **`__getattr__`** [#110]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/volumetric/VolumetricConnectomeAPI.py#L110) online

```python
def __getattr__(self, attr):
```  


no docstring

&nbsp;
## **`_get_structure_id`** [#124]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/volumetric/VolumetricConnectomeAPI.py#L124) online

```python
def _get_structure_id(self, struct):
```  


```text
Get the id of a structure (or list of structures) given it's
acronym
```

&nbsp;
## **`_load_voxel_data`** [#133]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/volumetric/VolumetricConnectomeAPI.py#L133) online

```python
def _load_voxel_data(self):
```  


```text
Load the voxeldata array from knox et al 2018
```

&nbsp;
## **`_get_coordinates_from_voxel_id`** [#170]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/volumetric/VolumetricConnectomeAPI.py#L170) online

```python
def _get_coordinates_from_voxel_id(self, p0, as_source=True):
```  


```text
Takes the index of a voxel and returns the 3d coordinates in
reference space.
the index number should be extracted with either a
source_mask or a target_mask.
if target_mask wa used set as_source as false.
:param p0: int
```

&nbsp;
## **`_get_mask_coords`** [#186]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/volumetric/VolumetricConnectomeAPI.py#L186) online

```python
def _get_mask_coords(self, as_source):
```  


no docstring

&nbsp;
## **`_get_voxel_id_from_coordinates`** [#201]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/volumetric/VolumetricConnectomeAPI.py#L201) online

```python
def _get_voxel_id_from_coordinates(self, p0, as_source=True):
```  


no docstring

&nbsp;
## **`_get_cache_filename`** [#223]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/volumetric/VolumetricConnectomeAPI.py#L223) online

```python
def _get_cache_filename(self, tgt, what):
```  


```text
Data are cached according to a naming convention, this
function gets the name for an object
according to the convention
```

&nbsp;
## **`_get_from_cache`** [#242]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/volumetric/VolumetricConnectomeAPI.py#L242) online

```python
def _get_from_cache(self, tgt, what):
```  


```text
Tries to load objects from cached data, if they exist
```

&nbsp;
## **`save_to_cache`** [#253]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/volumetric/VolumetricConnectomeAPI.py#L253) online

```python
def save_to_cache(self, tgt, what, obj):
```  


```text
Saves data to cache to avoid loading thema again in the
future
```

&nbsp;
## **`get_source`** [#264]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/volumetric/VolumetricConnectomeAPI.py#L264) online

```python
def get_source(self, source, hemisphere='both'):
```  


```text
Loads the mask for a source structure
:param source: str or list of str with acronym of source
regions
:param hemisphere: str, ['both', 'left', 'right'].  which
hemisphere to consider.
```

&nbsp;
## **`get_target_mask`** [#286]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/volumetric/VolumetricConnectomeAPI.py#L286) online

```python
def get_target_mask(self, target, hemisphere):
```  


```text
Returns a 'key' array and a mask object
used to transform projection data from linear arrays to 3d
volumes.
```

&nbsp;
## **`get_target`** [#297]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/volumetric/VolumetricConnectomeAPI.py#L297) online

```python
def get_target(self, target, hemisphere='both'):
```  


```text
Loads the mask for a target structure.
:param target: str or list of str with acronym of target
regions
:param hemisphere: str, ['both', 'left', 'right'].  which
hemisphere to consider.
```

&nbsp;
## **`get_projection`** [#327]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/volumetric/VolumetricConnectomeAPI.py#L327) online

```python
def get_projection(self, source, target, name, hemisphere='both', projection_mode='mean', mode='target'):
```  


```text
Gets the spatialised projection intensity from a source to a
target.
:param source: str or list of str with acronym of source
regions
:param target: str or list of str with acronym of target
regions
:param name: str, name of the projection
:param projection_mode: str, if 'mean' the data from
different experiments are averaged,
if 'max' the highest value is taken.
:param mode: str.  if 'target' the spatialised projection
strength in the target structures is returned, usefule
to see where source projects to in target.  otherwise if
'source' the spatialised projection strength in
the source structure is return.  useful to see which part of
source projects to target.
:return: 1d numpy array with mean projection from source to
target voxels
```

&nbsp;
## **`get_mapped_projection`** [#400]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/volumetric/VolumetricConnectomeAPI.py#L400) online

```python
def get_mapped_projection(self, source, target, name, **kwargs):
```  


```text
Gets the spatialised projection intensity from a source to a
target, but as
a mapped volume instead of a linear array.
:param source: str or list of str with acronym of source
regions
:param target: str or list of str with acronym of target
regions
:param name: str, name of the projection
:return: 3d numpy array with projectino intensity
```

&nbsp;
## **`get_mapped_projection_to_point`** [#416]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/volumetric/VolumetricConnectomeAPI.py#L416) online

```python
def get_mapped_projection_to_point(self, p0, restrict_to=None, restrict_to_hemisphere='both'):
```  


```text
Gets projection intensity from all voxels to the voxel
corresponding to a point of interest
```

&nbsp;
## **`get_mapped_projection_from_point`** [#452]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/volumetric/VolumetricConnectomeAPI.py#L452) online

```python
def get_mapped_projection_from_point(self, p0, restrict_to=None, restrict_to_hemisphere='both'):
```  


```text
Gets projection intensity from all voxels to the voxel
corresponding to a point of interest
```

&nbsp;
## **`add_mapped_projection`** [#497]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/volumetric/VolumetricConnectomeAPI.py#L497) online

```python
def add_mapped_projection(self, source, target, actor_kwargs={}, render_source_region=False, render_target_region=False, regions_kwargs={}, **kwargs):
```  


```text
Gets the spatialised projection intensity from a source to a
target
and renders it as a vedo lego visualisation.
:param source: str or list of str with acronym of source
regions
:param target: str or list of str with acronym of target
regions
:param render_source_region: bool, if true a wireframe mesh
of source regions is rendered
:param render_target_region: bool, if true a wireframe mesh
of target regions is rendered
:param regions_kwargs: pass options to specify how brain
regions should look like
:param kwargs: kwargs can be used to control how the
rendered object looks like.
look at the arguments of 'add_volume' to see what arguments
are available.
```

&nbsp;
## **`add_mapped_projection_to_point`** [#551]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/volumetric/VolumetricConnectomeAPI.py#L551) online

```python
def add_mapped_projection_to_point(self, p0, show_point=True, show_point_region=False, show_crosshair=True, crosshair_kwargs={}, point_region_kwargs={}, point_kwargs={}, from_point=False, **kwargs):
```  


no docstring

&nbsp;
## **`add_mapped_projection_from_point`** [#625]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/volumetric/VolumetricConnectomeAPI.py#L625) online

```python
def add_mapped_projection_from_point(self, *args, **kwargs):
```  


no docstring

&nbsp;
## **`add_volume`** [#630]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/volumetric/VolumetricConnectomeAPI.py#L630) online

```python
def add_volume(self, volume, cmap='afmhot_r', alpha=1, add_colorbar=True, **kwargs):
```  


```text
Renders intensitdata from a 3d numpy array as a lego
volumetric actor.
:param volume: np 3d array with number of dimensions = those
of the 100um reference space.
:param cmap: str with name of colormap to use
:param alpha: float, transparency
:param add_colorbar: if true a colorbar is added to show the
values of the colormap
```