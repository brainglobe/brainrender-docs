



Contents
========

* [**`get_scene_atlas`** [#12]](#get_scene_atlas-12)
* [**`get_scene_camera`** [#30]](#get_scene_camera-30)
* [**`get_scene_plotter_settings`** [#47]](#get_scene_plotter_settings-47)
* [**`get_cells_colors_from_metadata`** [#72]](#get_cells_colors_from_metadata-72)
* [**`make_actor_label`** [#115]](#make_actor_label-115)
* [**`get_n_random_points_in_region`** [#189]](#get_n_random_points_in_region-189)


&nbsp;

--------
# **`get_scene_atlas`** [#12]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/Utils/scene_utils.py#L12) online

```python
def get_scene_atlas(atlas, base_dir, atlas_kwargs={}, **kwargs):
```

&nbsp;  
docstring:

```text
Return an instance of an Atlas class.

```

&nbsp;

--------
# **`get_scene_camera`** [#30]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/Utils/scene_utils.py#L30) online

```python
def get_scene_camera(camera, atlas):
```

&nbsp;  
docstring:

```text
Gets a working camera.

In order these alternatives are used:

- user given camera

- atlas specific camera

- default camera

```

&nbsp;

--------
# **`get_scene_plotter_settings`** [#47]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/Utils/scene_utils.py#L47) online

```python
def get_scene_plotter_settings(jupyter):
```

&nbsp;  
docstring:

```text
Gets settings for vedo Plotter

```

&nbsp;

--------
# **`get_cells_colors_from_metadata`** [#72]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/Utils/scene_utils.py#L72) online

```python
def get_cells_colors_from_metadata(color_by_metadata, coords_df,
    color):
```

&nbsp;  
docstring:

```text
Get color of each cell given some metadata entry

:param color_by_metadata: str, column name with metadata info

:param coords_df: dataframe with cell coordinates and metadata

```

&nbsp;

--------
# **`make_actor_label`** [#115]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/Utils/scene_utils.py#L115) online

```python
def make_actor_label(atlas, actors, labels, size=300, color=None,
    radius=100, xoffset=0, yoffset=0, zoffset=0):
```

&nbsp;  
docstring:

```text
Adds a 2D text ancored to a point on the actor's mesh

to label what the actor is

:param kwargs: key word arguments can be passed to determine

text appearance and location:

- size: int, text size. Default 300

- color: str, text color. A list of colors can be passed

if None the actor's color is used. Default None.

- xoffset, yoffset, zoffset: integers that shift the label position

- radius: radius of sphere used to denote label anchor. Set to 0 or
    None to hide.

```

&nbsp;

--------
# **`get_n_random_points_in_region`** [#189]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/Utils/scene_utils.py#L189) online

```python
def get_n_random_points_in_region(atlas, region, N, hemisphere=None):
```

&nbsp;  
docstring:

```text
Gets N random points inside (or on the surface) of the mesh defining a
    brain region.

:param region: str, acronym of the brain region.

:param N: int, number of points to return.

```