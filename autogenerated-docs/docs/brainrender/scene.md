



Contents
========

* [**Scene**](#scene)
	* [**`__init__`** [#48]](#__init__-48)
	* [**`_check_point_in_region`** [#237]](#_check_point_in_region-237)
	* [**`_get_inset`** [#249]](#_get_inset-249)
	* [**`get_n_random_points_in_region`** [#277]](#get_n_random_points_in_region-277)
	* [**`edit_actors`** [#312]](#edit_actors-312)
	* [**`mirror_actor_hemisphere`** [#325]](#mirror_actor_hemisphere-325)
	* [**`cut_actors_with_plane`** [#338]](#cut_actors_with_plane-338)
	* [**`get_cells_in_region`** [#405]](#get_cells_in_region-405)
	* [**`add_root`** [#432]](#add_root-432)
	* [**`add_brain_regions`** [#456]](#add_brain_regions-456)
	* [**`add_neurons`** [#481]](#add_neurons-481)
	* [**`add_neurons_synapses`** [#499]](#add_neurons_synapses-499)
	* [**`add_tractography`** [#514]](#add_tractography-514)
	* [**`add_streamlines`** [#524]](#add_streamlines-524)
	* [**`add_actor`** [#534]](#add_actor-534)
	* [**`add_mesh_silhouette`** [#558]](#add_mesh_silhouette-558)
	* [**`add_from_file`** [#566]](#add_from_file-566)
	* [**`add_sphere_at_point`** [#582]](#add_sphere_at_point-582)
	* [**`add_cells_from_file`** [#600]](#add_cells_from_file-600)
	* [**`add_cells`** [#664]](#add_cells-664)
	* [**`add_optic_cannula`** [#768]](#add_optic_cannula-768)
	* [**`add_text`** [#838]](#add_text-838)
	* [**`add_actor_label`** [#857]](#add_actor_label-857)
	* [**`add_line_at_point`** [#935]](#add_line_at_point-935)
	* [**`add_rostrocaudal_line_at_point`** [#958]](#add_rostrocaudal_line_at_point-958)
	* [**`add_dorsoventral_line_at_point`** [#968]](#add_dorsoventral_line_at_point-968)
	* [**`add_mediolateral_line_at_point`** [#978]](#add_mediolateral_line_at_point-978)
	* [**`add_crosshair_at_point`** [#988]](#add_crosshair_at_point-988)
	* [**`add_plane`** [#1031]](#add_plane-1031)
	* [**`add_probe_from_sharptrack`** [#1070]](#add_probe_from_sharptrack-1070)
	* [**`apply_render_style`** [#1138]](#apply_render_style-1138)
	* [**`get_actors`** [#1157]](#get_actors-1157)
	* [**`render`** [#1179]](#render-1179)
	* [**`close`** [#1261]](#close-1261)
	* [**`export_for_web`** [#1264]](#export_for_web-1264)
	* [**`keypress`** [#1310]](#keypress-1310)
	* [**`take_screenshot`** [#1343]](#take_screenshot-1343)
* [**DualScene**](#dualscene)
	* [**`__init__`** [#1356]](#__init__-1356)
	* [**`render`** [#1359]](#render-1359)
	* [**`close`** [#1396]](#close-1396)
* [**MultiScene**](#multiscene)
	* [**`__init__`** [#1403]](#__init__-1403)
	* [**`render`** [#1416]](#render-1416)
	* [**`close`** [#1467]](#close-1467)


&nbsp;

--------
# **Scene**


```
The code below aims to create a scene to which actors can be added or removed, changed etc..
It also facilitates the interaction with the scene (e.g. moving the camera) and the creation of
snapshots or animated videos.
The class Scene is based on the Plotter class of vedo: https://github.com/marcomusy/vedo/blob/master/vedo/plotter.py
and other classes within the same package.
```

&nbsp;
## **`__init__`** [#48]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L48) online

```python
def __init__(self, brain_regions=None, regions_aba_color=False,
    neurons=None, tracts=None, add_root=None, verbose=True,
    ignore_jupyter=False, display_inset=None, base_dir=None, camera=None,
    screenshot_kwargs={}, use_default_key_bindings=False, title=None,
    atlas=None, atlas_kwargs=dict(), **kwargs):
```  


```text
Creates and manages a plotter instance

:param brain_regions: list of brain regions acronyms to be added to
    the rendered scene (default value none)

:param regions_aba_color: if true, use the allen brain atlas regions
    colors (default value none)

:param neurons: path to json or swc file with data of neurons to be
    rendered [or list of files] (default value none)

:param tracts: list of json files with tractography data to be
    rendered (default value none)

:param add_root: if false a rendered outline of the whole brain is
    added to the scene (default value none)

:param verbose: if false less feedback is printed to screen (default
    value true)

:param display_insert: if false the inset displaying the brain's
    outline is not rendered (but the root is added to the scene) (default
    value none)

:param base_dir: path to directory to use for saving data (default
    value none)

:param camera: name of the camera parameters setting to use (controls
    the orientation of the rendered scene)

:param kwargs: can be used to pass path to individual data folders.
    see brainrender/utils/paths_manager. Py

:param screenshot_kwargs: pass a dictionary with keys:

- 'folder' -> str, path to folder where to save screenshots

- 'name' -> str, filename to prepend to screenshots files

- 'format' -> str, 'png', 'svg' or 'jpg'

- scale -> float, values > 1 yield higher resultion screenshots

:param use_default_key_bindings: if true the defualt keybindings from
    vedo are used, otherwise

a custom function that can be used to take screenshots with the
    parameter above.

:param title: str, if a string is passed a text is added to the top of
    the rendering window as a title

:param atlas: str, class.  default none.  if a string is passed it
    whould be the name of a valide

brainglobe_api atlas.  alternative a class object can be passed, this
    should support the functionality

expected of an atlas class.

if no atlas is passed the allen brain atlas for the adult mouse brain
    is used.  if a string with the atlas

name is passed it will try to load the corresponding brainglobe atlas.

:param atlas_kwargs: dictionary used to pass extra arguments to atlas
    class

:param ignore_jupyter: bool, if false brainrender auto-detects if the
    user is using jupyter and adjusts to it

```

&nbsp;
## **`_check_point_in_region`** [#237]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L237) online

```python
def _check_point_in_region(self, point, region_actor):
```  


```text
Checks if a point of defined coordinates is within the mesh of a given
    actorr

:param point: 3-tuple or list of xyz coordinates

:param region_actor: vedo actor

```

&nbsp;
## **`_get_inset`** [#249]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L249) online

```python
def _get_inset(self, **kwargs):
```  


```text
Handles the rendering of the inset showing the outline of the whole
    brain (root) in a corner of the scene.

:param **kwargs:

```

&nbsp;
## **`get_n_random_points_in_region`** [#277]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L277) online

```python
def get_n_random_points_in_region(self, region, N, hemisphere=None):
```  


```text
Gets n random points inside (or on the surface) of the mesh defining a
    brain region.

:param region: str, acronym of the brain region.

:param n: int, number of points to return.

```

&nbsp;
## **`edit_actors`** [#312]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L312) online

```python
def edit_actors(self, actors, **kwargs):
```  


```text
Edits a list of actors (e. G.  render as wireframe or solid)

:param actors: list of actors

:param **kwargs:

```

&nbsp;
## **`mirror_actor_hemisphere`** [#325]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L325) online

```python
def mirror_actor_hemisphere(self, actors):
```  


```text
Mirrors actors from one hemisphere to the next

```

&nbsp;
## **`cut_actors_with_plane`** [#338]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L338) online

```python
def cut_actors_with_plane(self, plane, actors=None, showplane=False,
    returncut=False, close_actors=False, **kwargs):
```  


no docstring

&nbsp;
## **`get_cells_in_region`** [#405]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L405) online

```python
def get_cells_in_region(self, cells, region):
```  


```text
Selects the cells that are in a list of user provided regions from a
    dataframe of cell locations

:param cells: pd. Dataframe of cells x,y,z coordinates

```

&nbsp;
## **`add_root`** [#432]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L432) online

```python
def add_root(self, render=True, **kwargs):
```  


```text
Adds the root the scene (i. E.  the whole brain outline)

:param render:  (default value = true)

:param **kwargs:

```

&nbsp;
## **`add_brain_regions`** [#456]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L456) online

```python
def add_brain_regions(self, *args, **kwargs):
```  


```text
Adds brain regions meshes to scene.

check the atlas' method to know how it works

```

&nbsp;
## **`add_neurons`** [#481]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L481) online

```python
def add_neurons(self, *args, **kwargs):
```  


```text
Adds rendered morphological data of neurons reconstructions.

check the atlas' method to know how it works

```

&nbsp;
## **`add_neurons_synapses`** [#499]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L499) online

```python
def add_neurons_synapses(self, *args, **kwargs):
```  


```text
Adds the location of pre or post synapses for a neuron (or list of
    neurons).

check the atlas' method to know how it works.

```

&nbsp;
## **`add_tractography`** [#514]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L514) online

```python
def add_tractography(self, *args, **kwargs):
```  


```text
Renders tractography data and adds it to the scene.

check the function definition in aba for more details

```

&nbsp;
## **`add_streamlines`** [#524]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L524) online

```python
def add_streamlines(self, *args, **kwargs):
```  


```text
Render streamline data.

check the function definition in aba for more details

```

&nbsp;
## **`add_actor`** [#534]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L534) online

```python
def add_actor(self, *actors, store=None):
```  


```text
Add a vtk actor to the scene

:param actor:

:param store: one of the items in self. Actors to use to store the
    actor

being created.  it needs to be a list

```

&nbsp;
## **`add_mesh_silhouette`** [#558]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L558) online

```python
def add_mesh_silhouette(self, *actors, lw=1, color='k', **kwargs):
```  


```text
Given a list of actors it adds a colored silhouette

to them.

```

&nbsp;
## **`add_from_file`** [#566]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L566) online

```python
def add_from_file(self, *filepaths, **kwargs):
```  


```text
Add data to the scene by loading them from a file.  should handle .
    Obj, . Vtk and . Nii files.

:param filepaths: path to the file.  can pass as many arguments as
    needed

:param **kwargs:

```

&nbsp;
## **`add_sphere_at_point`** [#582]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L582) online

```python
def add_sphere_at_point(self, pos=[0, 0, 0], radius=100,
    color='black', alpha=1, **kwargs):
```  


```text
Adds a shere at a location specified by the user

:param pos: list of x,y,z coordinates (default value = [0, 0, 0])

:param radius: int, radius of the sphere (default value = 100)

:param color: color of the sphere (default value = "black")

:param alpha: transparency of the sphere (default value = 1)

:param **kwargs:

```

&nbsp;
## **`add_cells_from_file`** [#600]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L600) online

```python
def add_cells_from_file(self, filepath, hdf_key='hdf', color='red',
    radius=25, res=3, alpha=1):
```  


```text
Load location of cells from a file (csv and hdf) and render as spheres
    aligned to the root mesh.

:param filepath: str path to file

:param hdf_key: str (default value = none)

:param color: str, color of spheres used to render the cells (default
    value = "red")

:param radius: int, radius of spheres used to render the cells
    (default value = 25)

:param res: int, resolution of spheres used to render the cells
    (default value = 3)

:param alpha: float, transparency of spheres used to render the cells
    (default value = 1)

```

&nbsp;
## **`add_cells`** [#664]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L664) online

```python
def add_cells(self, coords, color='red', color_by_region=False,
    color_by_metadata=None, radius=25, res=3, alpha=1, col_names=None,
    regions=None, verbose=True):
```  


```text
Renders cells given their coordinates as a collection of spheres.

:param coords: pandas dataframe with x,y,z coordinates

:param color: str, color of spheres used to render the cells (default
    value = "red").

alternatively a list of colors specifying the color of each cell.

:param radius: int, radius of spheres used to render the cells
    (default value = 25)

:param res: int, resolution of spheres used to render the cells
    (default value = 3)

:param alpha: float, transparency of spheres used to render the cells
    (default value = 1)

:param color_by_region: bool.  if true the cells are colored according
    to the color of the brain region they are in

:param color_by_metadata: str, if the name of a column of the coords
    dataframe is passed, cells are colored according

to their value for that column.  if color_by_metadata is passed and a
    dictionary is passed

to 'color' at the same time, the dictionary will be used to specify
    the colors used.  therefore

`color` should map values in the metadata column to colors

:param regions: if a list of brain regions acronym is passed, only
    cells in these regions will be added to the scene

:param col_names: list of strings with names of pandas dataframe
    columns.  if passed it should be a list of 3 columns

which have the x, y, z coordinates.  if not passed, it is assumed that
    the columns are ['x', 'y', 'z']

```

&nbsp;
## **`add_optic_cannula`** [#768]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L768) online

```python
def add_optic_cannula(self, target_region=None, pos=None, x_offset=0,
    y_offset=0, z_offset=(- 500), use_line=False, **kwargs):
```  


```text
Adds a cylindrical vtk actor to scene to render optic cannulas.  by
    default

this is a semi-transparent blue cylinder centered on the center of
    mass of

a specified target region and oriented vertically.

:param target_region: str, acronym of target region to extract
    coordinates

of implanted fiber.  by defualt the fiber will be centered on the
    center

of mass of the target region but the offset arguments can be used to

fine tune the position.  alternative pass a 'pos' argument with xyz
    coords.

:param pos: list or tuple or np. Array with x,y,z coordinates.  must
    have length = 3.

:param x_offset, y_offset, z_offset: int, used to fine tune the
    coordinates of

the implanted cannula.

:param **kwargs: used to specify which hemisphere the cannula is and
    parameters

of the rendered cylinder: color, alpha, rotation axis. . .

```

&nbsp;
## **`add_text`** [#838]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L838) online

```python
def add_text(self, text, **kwargs):
```  


```text
Adds a 2d text to the scene.  default params are to crate a large
    black

text at the top of the rendering window.

:param text: str with text to write

:param kwargs: keyword arguments accepted by vedo. Shapes. Text2d

```

&nbsp;
## **`add_actor_label`** [#857]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L857) online

```python
def add_actor_label(self, actors, labels, **kwargs):
```  


```text
Adds a 2d text ancored to a point on the actor's mesh

to label what the actor is

:param kwargs: key word arguments can be passed to determine

text appearance and location:

- size: int, text size.  default 300

- color: str, text color.  a list of colors can be passed

if none the actor's color is used.  default none.

- xoffset, yoffset, zoffset: integers that shift the label position

- radius: radius of sphere used to denote label anchor.  set to 0 or
    none to hide.

```

&nbsp;
## **`add_line_at_point`** [#935]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L935) online

```python
def add_line_at_point(self, point, replace_coord, bounds, **kwargs):
```  


```text
Adds a line oriented on a given axis at a point

:param point:list or 1d np array with coordinates of point where
    crosshair is centered

:param replace_coord: index of the coordinate to replace (i. E.  along
    which axis is the line oriented)

:param bounds: list of two floats with lower and upper bound for line,
    determins the extent of the line

:param kwargs: dictionary with arguments to specify how lines should
    look like

```

&nbsp;
## **`add_rostrocaudal_line_at_point`** [#958]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L958) online

```python
def add_rostrocaudal_line_at_point(self, point, **kwargs):
```  


```text
Add a line at a point oriented along the trostrocaudal axis

:param point:list or 1d np array with coordinates of point where
    crosshair is centered

:param line_kwargs: dictionary with arguments to specify how lines
    should look like

```

&nbsp;
## **`add_dorsoventral_line_at_point`** [#968]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L968) online

```python
def add_dorsoventral_line_at_point(self, point, **kwargs):
```  


```text
Add a line at a point oriented along the mdorsoventralediolateral axis

:param point:list or 1d np array with coordinates of point where
    crosshair is centered

:param line_kwargs: dictionary with arguments to specify how lines
    should look like

```

&nbsp;
## **`add_mediolateral_line_at_point`** [#978]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L978) online

```python
def add_mediolateral_line_at_point(self, point, **kwargs):
```  


```text
Add a line at a point oriented along the mediolateral axis

:param point:list or 1d np array with coordinates of point where
    crosshair is centered

:param line_kwargs: dictionary with arguments to specify how lines
    should look like

```

&nbsp;
## **`add_crosshair_at_point`** [#988]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L988) online

```python
def add_crosshair_at_point(self, point, ml=True, dv=True, ap=True,
    show_point=True, line_kwargs={}, point_kwargs={}):
```  


```text
Add a crosshair (set of orthogonal lines meeting at a point)

centered on a given point.

:param point: list or 1d np array with coordinates of point where
    crosshair is centered

:param ml: bool, if true a line oriented on the mediolateral axis is
    added

:param dv: bool, if true a line oriented on the dorsoventral axis is
    added

:param ap: bool, if true a line oriented on the anteriorposterior or
    rostsrocaudal axis is added

:param show_point: bool, if true a sphere at the loation of the point
    is shown

:param line_kwargs: dictionary with arguments to specify how lines
    should look like

:param point_kwargs: dictionary with arguments to specify how the
    point should look

```

&nbsp;
## **`add_plane`** [#1031]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L1031) online

```python
def add_plane(self, plane, **kwargs):
```  


```text
Adds one or more planes to the scene.

for more details on how to build custom planes, check:

brainrender/atlases/base. Py -> base. Get_plane_at_point

method.

:param plane: either a string with the name of one of

the predifined planes ['sagittal', 'coronal', 'horizontal']

or an instance of the plane class from vedo. Shapes

```

&nbsp;
## **`add_probe_from_sharptrack`** [#1070]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L1070) online

```python
def add_probe_from_sharptrack(self, probe_points_file,
    points_kwargs={}, **kwargs):
```  


```text
Visualises the position of an implanted probe in the brain.

uses the location of points along the probe extracted with sharptrack

[https://github. Com/cortex-lab/allenccf].

it renders the position of points along the probe and a line fit
    through them.

code contributed by @tbslv on github.

:param probe_points_file: str, path to a . Mat file with probe points
    coordinates

:param points_kwargs: dict, used to specify how probe points should
    look like (e. G color, alpha. . . )

:param kwargs: keyword arguments used to specify how the probe should
    look like (e. G.  color, alpha. . . )

```

&nbsp;
## **`apply_render_style`** [#1138]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L1138) online

```python
def apply_render_style(self):
```  


no docstring

&nbsp;
## **`get_actors`** [#1157]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L1157) online

```python
def get_actors(self):
```  


no docstring

&nbsp;
## **`render`** [#1179]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L1179) online

```python
def render(self, interactive=True, video=False, camera=None,
    zoom=None, **kwargs):
```  


```text
Takes care of rendering the scene

```

&nbsp;
## **`close`** [#1261]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L1261) online

```python
def close(self):
```  


no docstring

&nbsp;
## **`export_for_web`** [#1264]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L1264) online

```python
def export_for_web(self, filepath='brexport.html'):
```  


```text
This function is used to export a brainrender scene

for hosting it online.  it saves an html file that can

be opened in a web browser to show an interactive brainrender scene

```

&nbsp;
## **`keypress`** [#1310]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L1310) online

```python
def keypress(self, key):
```  


no docstring

&nbsp;
## **`take_screenshot`** [#1343]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L1343) online

```python
def take_screenshot(self):
```  


no docstring

&nbsp;

--------
# **DualScene**


```

```

&nbsp;
## **`__init__`** [#1356]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L1356) online

```python
def __init__(self, *args, **kwargs):
```  


no docstring

&nbsp;
## **`render`** [#1359]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L1359) online

```python
def render(self, _interactive=True):
```  


```text

```

&nbsp;
## **`close`** [#1396]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L1396) online

```python
def close(self):
```  


no docstring

&nbsp;

--------
# **MultiScene**


```

```

&nbsp;
## **`__init__`** [#1403]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L1403) online

```python
def __init__(self, N, scenes=None, *args, **kwargs):
```  


no docstring

&nbsp;
## **`render`** [#1416]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L1416) online

```python
def render(self, _interactive=True, **kwargs):
```  


```text
:param _interactive:  (default value = true)

:param **kwargs:

```

&nbsp;
## **`close`** [#1467]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L1467) online

```python
def close(self):
```  


no docstring