



Contents
========

* [**Scene**](#scene)
	* [**`__init__`** [#46]](#__init__-46)
	* [**`__str__`** [#115]](#__str__-115)
	* [**`__repr__`** [#118]](#__repr__-118)
	* [**`__add__`** [#121]](#__add__-121)
	* [**`__iadd__`** [#129]](#__iadd__-129)
	* [**`__len__`** [#133]](#__len__-133)
	* [**`__getitem__`** [#136]](#__getitem__-136)
	* [**`__del__`** [#139]](#__del__-139)
	* [**`_get_inset`** [#146]](#_get_inset-146)
	* [**`cut_actors_with_plane`** [#174]](#cut_actors_with_plane-174)
	* [**`list_actors`** [#239]](#list_actors-239)
	* [**`add_root`** [#262]](#add_root-262)
	* [**`add_brain_regions`** [#297]](#add_brain_regions-297)
	* [**`add_neurons`** [#324]](#add_neurons-324)
	* [**`add_neurons_synapses`** [#356]](#add_neurons_synapses-356)
	* [**`add_tractography`** [#373]](#add_tractography-373)
	* [**`add_streamlines`** [#388]](#add_streamlines-388)
	* [**`add_actor`** [#403]](#add_actor-403)
	* [**`add_silhouette`** [#418]](#add_silhouette-418)
	* [**`add_from_file`** [#430]](#add_from_file-430)
	* [**`add_sphere_at_point`** [#447]](#add_sphere_at_point-447)
	* [**`add_cells_from_file`** [#467]](#add_cells_from_file-467)
	* [**`add_cells`** [#492]](#add_cells-492)
	* [**`add_optic_cannula`** [#560]](#add_optic_cannula-560)
	* [**`add_text`** [#591]](#add_text-591)
	* [**`add_actor_label`** [#607]](#add_actor_label-607)
	* [**`add_line_at_point`** [#627]](#add_line_at_point-627)
	* [**`add_crosshair_at_point`** [#653]](#add_crosshair_at_point-653)
	* [**`add_plane`** [#670]](#add_plane-670)
	* [**`add_ruler_from_surface`** [#705]](#add_ruler_from_surface-705)
	* [**`add_probe_from_sharptrack`** [#729]](#add_probe_from_sharptrack-729)
* [**DualScene**](#dualscene)
	* [**`__init__`** [#767]](#__init__-767)
	* [**`render`** [#770]](#render-770)
	* [**`close`** [#800]](#close-800)
* [**MultiScene**](#multiscene)
	* [**`__init__`** [#807]](#__init__-807)
	* [**`render`** [#820]](#render-820)
	* [**`close`** [#866]](#close-866)


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
## **`__init__`** [#46]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/scene.py#L46) online

```python
def __init__(self, add_root=None, verbose=True, display_inset=None,
    base_dir=None, camera=None, screenshot_kwargs={},
    use_default_key_bindings=False, title=None, atlas=None,
    atlas_kwargs=dict(), **kwargs):
```

&nbsp;  
docstring:

```text
Creates and manages a Plotter instance

:param add_root: if False a rendered outline of the whole brain is
    added to the scene (default value None)

:param verbose: if False less feedback is printed to screen (default
    value True)

:param display_insert: if False the inset displaying the brain's
    outline is not rendered (but the root is added to the scene) (default
    value None)

:param base_dir: path to directory to use for saving data (default
    value None)

:param camera: name of the camera parameters setting to use (controls
    the orientation of the rendered scene)

:param kwargs: can be used to pass path to individual data folders.
    See brainrender/Utils/paths_manager.py

:param screenshot_kwargs: pass a dictionary with keys:

- 'folder' -> str, path to folder where to save screenshots

- 'name' -> str, filename to prepend to screenshots files

- 'format' -> str, 'png', 'svg' or 'jpg'

- scale -> float, values > 1 yield higher resultion screenshots

:param use_default_key_bindings: if True the defualt keybindings from
    vedo are used, otherwise

a custom function that can be used to take screenshots with the
    parameter above.

:param title: str, if a string is passed a text is added to the top of
    the rendering window as a title

:param atlas: str, class. Default None. If a string is passed it
    whould be the name of a valide

brainglobe_api atlas. Alternative a class object can be passed, this
    should support the functionality

expected of an atlas class.

if no atlas is passed the allen brain atlas for the adult mouse brain
    is used. If a string with the atlas

name is passed it will try to load the corresponding brainglobe atlas.

:param atlas_kwargs: dictionary used to pass extra arguments to atlas
    class

```

&nbsp;
## **`__str__`** [#115]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/scene.py#L115) online

```python
def __str__(self):
```

&nbsp;  
docstring:

no docstring

&nbsp;
## **`__repr__`** [#118]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/scene.py#L118) online

```python
def __repr__(self):
```

&nbsp;  
docstring:

no docstring

&nbsp;
## **`__add__`** [#121]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/scene.py#L121) online

```python
def __add__(self, other):
```

&nbsp;  
docstring:

no docstring

&nbsp;
## **`__iadd__`** [#129]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/scene.py#L129) online

```python
def __iadd__(self, other):
```

&nbsp;  
docstring:

no docstring

&nbsp;
## **`__len__`** [#133]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/scene.py#L133) online

```python
def __len__(self):
```

&nbsp;  
docstring:

no docstring

&nbsp;
## **`__getitem__`** [#136]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/scene.py#L136) online

```python
def __getitem__(self, index):
```

&nbsp;  
docstring:

no docstring

&nbsp;
## **`__del__`** [#139]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/scene.py#L139) online

```python
def __del__(self):
```

&nbsp;  
docstring:

no docstring

&nbsp;
## **`_get_inset`** [#146]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/scene.py#L146) online

```python
def _get_inset(self, **kwargs):
```

&nbsp;  
docstring:

```text
Handles the rendering of the inset showing the outline of the whole
    brain (root) in a corner of the scene.

:param **kwargs:

```

&nbsp;
## **`cut_actors_with_plane`** [#174]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/scene.py#L174) online

```python
def cut_actors_with_plane(self, plane, actors=None, showplane=False,
    returncut=False, close_actors=False, **kwargs):
```

&nbsp;  
docstring:

no docstring

&nbsp;
## **`list_actors`** [#239]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/scene.py#L239) online

```python
def list_actors(self):
```

&nbsp;  
docstring:

no docstring

&nbsp;
## **`add_root`** [#262]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/scene.py#L262) online

```python
def add_root(self, render=True, **kwargs):
```

&nbsp;  
docstring:

```text
adds the root the scene (i.e. the whole brain outline)

:param render:  (Default value = True)

:param **kwargs:

```

&nbsp;
## **`add_brain_regions`** [#297]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/scene.py#L297) online

```python
def add_brain_regions(self, *args, **kwargs):
```

&nbsp;  
docstring:

```text
Adds brain regions meshes to scene.

Check the atlas' method to know how it works

```

&nbsp;
## **`add_neurons`** [#324]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/scene.py#L324) online

```python
def add_neurons(self, *args, **kwargs):
```

&nbsp;  
docstring:

```text
Adds rendered morphological data of neurons reconstructions.

Check the atlas' method to know how it works

```

&nbsp;
## **`add_neurons_synapses`** [#356]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/scene.py#L356) online

```python
def add_neurons_synapses(self, *args, **kwargs):
```

&nbsp;  
docstring:

```text
Adds the location of pre or post synapses for a neuron (or list of
    neurons).

Check the atlas' method to know how it works.

```

&nbsp;
## **`add_tractography`** [#373]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/scene.py#L373) online

```python
def add_tractography(self, *args, **kwargs):
```

&nbsp;  
docstring:

```text
Renders tractography data and adds it to the scene.

Check the function definition in ABA for more details

```

&nbsp;
## **`add_streamlines`** [#388]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/scene.py#L388) online

```python
def add_streamlines(self, *args, **kwargs):
```

&nbsp;  
docstring:

```text
Render streamline data.

Check the function definition in ABA for more details

```

&nbsp;
## **`add_actor`** [#403]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/scene.py#L403) online

```python
def add_actor(self, *actors, store=None):
```

&nbsp;  
docstring:

```text
Add a vtk actor to the scene

:param actor:

:param store: a list to store added actors

```

&nbsp;
## **`add_silhouette`** [#418]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/scene.py#L418) online

```python
def add_silhouette(self, *actors, lw=1, color='k', **kwargs):
```

&nbsp;  
docstring:

```text
Given a list of actors it adds a colored silhouette

to them.

```

&nbsp;
## **`add_from_file`** [#430]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/scene.py#L430) online

```python
def add_from_file(self, *filepaths, **kwargs):
```

&nbsp;  
docstring:

```text
Add data to the scene by loading them from a file. Should handle .obj,
    .vtk and .nii files.

:param filepaths: path to the file. Can pass as many arguments as
    needed

:param **kwargs:

```

&nbsp;
## **`add_sphere_at_point`** [#447]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/scene.py#L447) online

```python
def add_sphere_at_point(self, pos=[0, 0, 0], radius=100,
    color='black', alpha=1, **kwargs):
```

&nbsp;  
docstring:

```text
Adds a shere at a location specified by the user

:param pos: list of x,y,z coordinates (Default value = [0, 0, 0])

:param radius: int, radius of the sphere (Default value = 100)

:param color: color of the sphere (Default value = "black")

:param alpha: transparency of the sphere (Default value = 1)

:param **kwargs:

```

&nbsp;
## **`add_cells_from_file`** [#467]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/scene.py#L467) online

```python
def add_cells_from_file(self, filepath, hdf_key='hdf', color='red',
    radius=25, res=7, alpha=1):
```

&nbsp;  
docstring:

```text
Load location of cells from a file (csv and HDF) and render as spheres
    aligned to the root mesh.

:param filepath: str path to file

:param hdf_key: str (Default value = None)

:param color: str, color of spheres used to render the cells (Default
    value = "red")

:param radius: int, radius of spheres used to render the cells
    (Default value = 25)

:param res: int, resolution of spheres used to render the cells
    (Default value = 3)

:param alpha: float, transparency of spheres used to render the cells
    (Default value = 1)

```

&nbsp;
## **`add_cells`** [#492]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/scene.py#L492) online

```python
def add_cells(self, coords, color='red', color_by_region=False,
    color_by_metadata=None, radius=25, res=7, alpha=1, col_names=None,
    regions=None, verbose=True):
```

&nbsp;  
docstring:

```text
Renders cells given their coordinates as a collection of spheres.

:param coords: pandas dataframe with x,y,z coordinates

:param color: str, color of spheres used to render the cells (Default
    value = "red").

Alternatively a list of colors specifying the color of each cell.

:param radius: int, radius of spheres used to render the cells
    (Default value = 25)

:param res: int, resolution of spheres used to render the cells
    (Default value = 3)

:param alpha: float, transparency of spheres used to render the cells
    (Default value = 1)

:param color_by_region: bool. If true the cells are colored according
    to the color of the brain region they are in

:param color_by_metadata: str, if the name of a column of the coords
    dataframe is passed, cells are colored according

to their value for that column. If color_by_metadata is passed and a
    dictionary is passed

to 'color' at the same time, the dictionary will be used to specify
    the colors used. Therefore

`color` should map values in the metadata column to colors

:param regions: if a list of brain regions acronym is passed, only
    cells in these regions will be added to the scene

:param col_names: list of strings with names of pandas dataframe
    columns. If passed it should be a list of 3 columns

which have the x, y, z coordinates. If not passed, it is assumed that
    the columns are ['x', 'y', 'z']

```

&nbsp;
## **`add_optic_cannula`** [#560]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/scene.py#L560) online

```python
def add_optic_cannula(self, *args, **kwargs):
```

&nbsp;  
docstring:

```text
Adds a cylindrical vedo actor to scene to render optic cannulas. By
    default

this is a semi-transparent blue cylinder centered on the center of
    mass of

a specified target region and oriented vertically. Parameters are
    specified

as keyword arguments.

:param target_region: str, acronym of target region to extract
    coordinates

of implanted fiber. By defualt the fiber will be centered on the
    center

of mass of the target region but the offset arguments can be used to

fine tune the position. Alternative pass a 'pos' argument with AP-DV-
    ML coords.

:param pos: list or tuple or np.array with X,Y,Z coordinates. Must
    have length = 3.

:param x_offset, y_offset, z_offset: int, used to fine tune the
    coordinates of

the implanted cannula.

:param **kwargs: used to specify which hemisphere the cannula is and
    parameters

of the rendered cylinder: color, alpha, rotation axis...

```

&nbsp;
## **`add_text`** [#591]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/scene.py#L591) online

```python
def add_text(self, text, pos=8, size=2.5, color='k', alpha=1,
    font='Montserrat'):
```

&nbsp;  
docstring:

```text
Adds a 2D text to the scene. Default params are to crate a large black

text at the top of the rendering window.

:param text: str with text to write

:param kwargs: keyword arguments accepted by vedo.shapes.Text2D

```

&nbsp;
## **`add_actor_label`** [#607]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/scene.py#L607) online

```python
def add_actor_label(self, actors, labels, **kwargs):
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
## **`add_line_at_point`** [#627]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/scene.py#L627) online

```python
def add_line_at_point(self, point, axis, color='blackboard', lw=3,
    **kwargs):
```

&nbsp;  
docstring:

```text
Adds a line oriented on a given axis at a point

:param point:list or 1d np array with coordinates of point where
    crosshair is centered

:param replace_coord: index of the coordinate to replace (i.e. along
    which axis is the line oriented)

:param bounds: list of two floats with lower and upper bound for line,
    determins the extent of the line

:param kwargs: dictionary with arguments to specify how lines should
    look like

```

&nbsp;
## **`add_crosshair_at_point`** [#653]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/scene.py#L653) online

```python
def add_crosshair_at_point(self, point, show_point=True,
    line_kwargs={}, point_kwargs={}):
```

&nbsp;  
docstring:

```text
Add a crosshair (set of orthogonal lines meeting at a point)

centered on a given point.

:param point: list or 1d np array with coordinates of point where
    crosshair is centered

:param show_point: bool, if True a sphere at the loation of the point
    is shown

:param line_kwargs: dictionary with arguments to specify how lines
    should look like

:param point_kwargs: dictionary with arguments to specify how the
    point should look

```

&nbsp;
## **`add_plane`** [#670]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/scene.py#L670) online

```python
def add_plane(self, plane, **kwargs):
```

&nbsp;  
docstring:

```text
Adds one or more planes to the scene.

For more details on how to build custom planes, check:

brainrender/atlases/base.py -> Base.get_plane_at_point

method.

:param plane: either a string with the name of one of

the predifined planes ['sagittal', 'coronal', 'horizontal']

or an instance of the Plane class from vedo.shapes

```

&nbsp;
## **`add_ruler_from_surface`** [#705]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/scene.py#L705) online

```python
def add_ruler_from_surface(self, p0, axis=1):
```

&nbsp;  
docstring:

```text
Given a point, this function adds a ruler object showing

the distance of that point from the brain surface along a

given axis.

:param p0: np.array with point coordinates

:param axis: int, index of the axis along

which to measure distance

```

&nbsp;
## **`add_probe_from_sharptrack`** [#729]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/scene.py#L729) online

```python
def add_probe_from_sharptrack(self, probe_points_file,
    points_kwargs={}, name=None, **kwargs):
```

&nbsp;  
docstring:

```text
Visualises the position of an implanted probe in the brain.

Uses the location of points along the probe extracted with SharpTrack

[https://github.com/cortex-lab/allenCCF].

It renders the position of points along the probe and a line fit
    through them.

Code contributed by @tbslv on github.

:param probe_points_file: str, path to a .mat file with probe points
    coordinates

:param kwargs: keyword arguments used to specify how the probe and the
    poitns

should look like (e.g. color, alpha...)

```

&nbsp;

--------
# **DualScene**


```

```

&nbsp;
## **`__init__`** [#767]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/scene.py#L767) online

```python
def __init__(self, *args, **kwargs):
```

&nbsp;  
docstring:

no docstring

&nbsp;
## **`render`** [#770]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/scene.py#L770) online

```python
def render(self, _interactive=True):
```

&nbsp;  
docstring:

```text

```

&nbsp;
## **`close`** [#800]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/scene.py#L800) online

```python
def close(self):
```

&nbsp;  
docstring:

no docstring

&nbsp;

--------
# **MultiScene**


```

```

&nbsp;
## **`__init__`** [#807]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/scene.py#L807) online

```python
def __init__(self, N, scenes=None, *args, **kwargs):
```

&nbsp;  
docstring:

no docstring

&nbsp;
## **`render`** [#820]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/scene.py#L820) online

```python
def render(self, _interactive=True, **kwargs):
```

&nbsp;  
docstring:

```text
:param _interactive:  (Default value = True)

:param **kwargs:

```

&nbsp;
## **`close`** [#866]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/scene.py#L866) online

```python
def close(self):
```

&nbsp;  
docstring:

no docstring