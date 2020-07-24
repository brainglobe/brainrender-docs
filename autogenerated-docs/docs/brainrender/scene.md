



Contents
========

* [**Scene**](#scene)
	* [**`__init__`** [#49]](#__init__-49)
	* [**`_check_point_in_region`** [#239]](#_check_point_in_region-239)
	* [**`_get_inset`** [#251]](#_get_inset-251)
	* [**`get_n_random_points_in_region`** [#279]](#get_n_random_points_in_region-279)
	* [**`edit_actors`** [#314]](#edit_actors-314)
	* [**`mirror_actor_hemisphere`** [#327]](#mirror_actor_hemisphere-327)
	* [**`cut_actors_with_plane`** [#340]](#cut_actors_with_plane-340)
	* [**`get_cells_in_region`** [#407]](#get_cells_in_region-407)
	* [**`add_root`** [#434]](#add_root-434)
	* [**`add_brain_regions`** [#460]](#add_brain_regions-460)
	* [**`add_neurons`** [#486]](#add_neurons-486)
	* [**`add_neurons_synapses`** [#504]](#add_neurons_synapses-504)
	* [**`add_tractography`** [#519]](#add_tractography-519)
	* [**`add_streamlines`** [#529]](#add_streamlines-529)
	* [**`add_actor`** [#539]](#add_actor-539)
	* [**`add_mesh_silhouette`** [#563]](#add_mesh_silhouette-563)
	* [**`add_from_file`** [#571]](#add_from_file-571)
	* [**`add_sphere_at_point`** [#588]](#add_sphere_at_point-588)
	* [**`add_cells_from_file`** [#607]](#add_cells_from_file-607)
	* [**`add_cells`** [#631]](#add_cells-631)
	* [**`add_optic_cannula`** [#735]](#add_optic_cannula-735)
	* [**`add_text`** [#805]](#add_text-805)
	* [**`add_actor_label`** [#824]](#add_actor_label-824)
	* [**`add_line_at_point`** [#902]](#add_line_at_point-902)
	* [**`add_rostrocaudal_line_at_point`** [#925]](#add_rostrocaudal_line_at_point-925)
	* [**`add_dorsoventral_line_at_point`** [#935]](#add_dorsoventral_line_at_point-935)
	* [**`add_mediolateral_line_at_point`** [#945]](#add_mediolateral_line_at_point-945)
	* [**`add_crosshair_at_point`** [#955]](#add_crosshair_at_point-955)
	* [**`add_plane`** [#998]](#add_plane-998)
	* [**`add_probe_from_sharptrack`** [#1037]](#add_probe_from_sharptrack-1037)
	* [**`apply_render_style`** [#1106]](#apply_render_style-1106)
	* [**`get_actors`** [#1125]](#get_actors-1125)
	* [**`render`** [#1147]](#render-1147)
	* [**`close`** [#1229]](#close-1229)
	* [**`export_for_web`** [#1232]](#export_for_web-1232)
	* [**`keypress`** [#1278]](#keypress-1278)
	* [**`take_screenshot`** [#1311]](#take_screenshot-1311)
* [**DualScene**](#dualscene)
	* [**`__init__`** [#1324]](#__init__-1324)
	* [**`render`** [#1327]](#render-1327)
	* [**`close`** [#1364]](#close-1364)
* [**MultiScene**](#multiscene)
	* [**`__init__`** [#1371]](#__init__-1371)
	* [**`render`** [#1384]](#render-1384)
	* [**`close`** [#1435]](#close-1435)


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
## **`__init__`** [#49]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/scene.py#L49) online

```python
def __init__(self, brain_regions=None, regions_aba_color=False,
    neurons=None, tracts=None, add_root=None, verbose=True,
    ignore_jupyter=False, display_inset=None, base_dir=None, camera=None,
    screenshot_kwargs={}, use_default_key_bindings=False, title=None,
    atlas=None, atlas_kwargs=dict(), **kwargs):
```

&nbsp;  
docstring:

```text
Creates and manages a Plotter instance

:param brain_regions: list of brain regions acronyms to be added to
    the rendered scene (default value None)

:param regions_aba_color: if True, use the Allen Brain Atlas regions
    colors (default value None)

:param neurons: path to JSON or SWC file with data of neurons to be
    rendered [or list of files] (default value None)

:param tracts: list of JSON files with tractography data to be
    rendered (default value None)

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

:param ignore_jupyter: bool, if False brainrender auto-detects if the
    user is using jupyter and adjusts to it

```

&nbsp;
## **`_check_point_in_region`** [#239]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/scene.py#L239) online

```python
def _check_point_in_region(self, point, region_actor):
```

&nbsp;  
docstring:

```text
Checks if a point of defined coordinates is within the mesh of a given
    actorr

:param point: 3-tuple or list of xyz coordinates

:param region_actor: vedo actor

```

&nbsp;
## **`_get_inset`** [#251]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/scene.py#L251) online

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
## **`get_n_random_points_in_region`** [#279]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/scene.py#L279) online

```python
def get_n_random_points_in_region(self, region, N, hemisphere=None):
```

&nbsp;  
docstring:

```text
Gets N random points inside (or on the surface) of the mesh defining a
    brain region.

:param region: str, acronym of the brain region.

:param N: int, number of points to return.

```

&nbsp;
## **`edit_actors`** [#314]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/scene.py#L314) online

```python
def edit_actors(self, actors, **kwargs):
```

&nbsp;  
docstring:

```text
edits a list of actors (e.g. render as wireframe or solid)

:param actors: list of actors

:param **kwargs:

```

&nbsp;
## **`mirror_actor_hemisphere`** [#327]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/scene.py#L327) online

```python
def mirror_actor_hemisphere(self, actors):
```

&nbsp;  
docstring:

```text
Mirrors actors from one hemisphere to the next

```

&nbsp;
## **`cut_actors_with_plane`** [#340]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/scene.py#L340) online

```python
def cut_actors_with_plane(self, plane, actors=None, showplane=False,
    returncut=False, close_actors=False, **kwargs):
```

&nbsp;  
docstring:

no docstring

&nbsp;
## **`get_cells_in_region`** [#407]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/scene.py#L407) online

```python
def get_cells_in_region(self, cells, region):
```

&nbsp;  
docstring:

```text
Selects the cells that are in a list of user provided regions from a
    dataframe of cell locations

:param cells: pd.DataFrame of cells x,y,z coordinates

```

&nbsp;
## **`add_root`** [#434]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/scene.py#L434) online

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
## **`add_brain_regions`** [#460]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/scene.py#L460) online

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
## **`add_neurons`** [#486]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/scene.py#L486) online

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
## **`add_neurons_synapses`** [#504]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/scene.py#L504) online

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
## **`add_tractography`** [#519]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/scene.py#L519) online

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
## **`add_streamlines`** [#529]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/scene.py#L529) online

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
## **`add_actor`** [#539]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/scene.py#L539) online

```python
def add_actor(self, *actors, store=None):
```

&nbsp;  
docstring:

```text
Add a vtk actor to the scene

:param actor:

:param store: one of the items in self.actors to use to store the
    actor

being created. It needs to be a list

```

&nbsp;
## **`add_mesh_silhouette`** [#563]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/scene.py#L563) online

```python
def add_mesh_silhouette(self, *actors, lw=1, color='k', **kwargs):
```

&nbsp;  
docstring:

```text
Given a list of actors it adds a colored silhouette

to them.

```

&nbsp;
## **`add_from_file`** [#571]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/scene.py#L571) online

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
## **`add_sphere_at_point`** [#588]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/scene.py#L588) online

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
## **`add_cells_from_file`** [#607]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/scene.py#L607) online

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
## **`add_cells`** [#631]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/scene.py#L631) online

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
## **`add_optic_cannula`** [#735]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/scene.py#L735) online

```python
def add_optic_cannula(self, target_region=None, pos=None, x_offset=0,
    y_offset=0, z_offset=(- 500), use_line=False, **kwargs):
```

&nbsp;  
docstring:

```text
Adds a cylindrical vtk actor to scene to render optic cannulas. By
    default

this is a semi-transparent blue cylinder centered on the center of
    mass of

a specified target region and oriented vertically.

:param target_region: str, acronym of target region to extract
    coordinates

of implanted fiber. By defualt the fiber will be centered on the
    center

of mass of the target region but the offset arguments can be used to

fine tune the position. Alternative pass a 'pos' argument with XYZ
    coords.

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
## **`add_text`** [#805]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/scene.py#L805) online

```python
def add_text(self, text, **kwargs):
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
## **`add_actor_label`** [#824]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/scene.py#L824) online

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
## **`add_line_at_point`** [#902]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/scene.py#L902) online

```python
def add_line_at_point(self, point, replace_coord, bounds, **kwargs):
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
## **`add_rostrocaudal_line_at_point`** [#925]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/scene.py#L925) online

```python
def add_rostrocaudal_line_at_point(self, point, **kwargs):
```

&nbsp;  
docstring:

```text
Add a line at a point oriented along the trostrocaudal axis

:param point:list or 1d np array with coordinates of point where
    crosshair is centered

:param line_kwargs: dictionary with arguments to specify how lines
    should look like

```

&nbsp;
## **`add_dorsoventral_line_at_point`** [#935]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/scene.py#L935) online

```python
def add_dorsoventral_line_at_point(self, point, **kwargs):
```

&nbsp;  
docstring:

```text
Add a line at a point oriented along the mdorsoventralediolateral axis

:param point:list or 1d np array with coordinates of point where
    crosshair is centered

:param line_kwargs: dictionary with arguments to specify how lines
    should look like

```

&nbsp;
## **`add_mediolateral_line_at_point`** [#945]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/scene.py#L945) online

```python
def add_mediolateral_line_at_point(self, point, **kwargs):
```

&nbsp;  
docstring:

```text
Add a line at a point oriented along the mediolateral axis

:param point:list or 1d np array with coordinates of point where
    crosshair is centered

:param line_kwargs: dictionary with arguments to specify how lines
    should look like

```

&nbsp;
## **`add_crosshair_at_point`** [#955]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/scene.py#L955) online

```python
def add_crosshair_at_point(self, point, ml=True, dv=True, ap=True,
    show_point=True, line_kwargs={}, point_kwargs={}):
```

&nbsp;  
docstring:

```text
Add a crosshair (set of orthogonal lines meeting at a point)

centered on a given point.

:param point: list or 1d np array with coordinates of point where
    crosshair is centered

:param ml: bool, if True a line oriented on the mediolateral axis is
    added

:param dv: bool, if True a line oriented on the dorsoventral axis is
    added

:param ap: bool, if True a line oriented on the anteriorposterior or
    rostsrocaudal axis is added

:param show_point: bool, if True a sphere at the loation of the point
    is shown

:param line_kwargs: dictionary with arguments to specify how lines
    should look like

:param point_kwargs: dictionary with arguments to specify how the
    point should look

```

&nbsp;
## **`add_plane`** [#998]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/scene.py#L998) online

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
## **`add_probe_from_sharptrack`** [#1037]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/scene.py#L1037) online

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

:param points_kwargs: dict, used to specify how probe points should
    look like (e.g color, alpha...)

:param kwargs: keyword arguments used to specify how the probe should
    look like (e.g. color, alpha...)

```

&nbsp;
## **`apply_render_style`** [#1106]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/scene.py#L1106) online

```python
def apply_render_style(self):
```

&nbsp;  
docstring:

no docstring

&nbsp;
## **`get_actors`** [#1125]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/scene.py#L1125) online

```python
def get_actors(self):
```

&nbsp;  
docstring:

no docstring

&nbsp;
## **`render`** [#1147]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/scene.py#L1147) online

```python
def render(self, interactive=True, video=False, camera=None,
    zoom=None, **kwargs):
```

&nbsp;  
docstring:

```text
Takes care of rendering the scene

```

&nbsp;
## **`close`** [#1229]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/scene.py#L1229) online

```python
def close(self):
```

&nbsp;  
docstring:

no docstring

&nbsp;
## **`export_for_web`** [#1232]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/scene.py#L1232) online

```python
def export_for_web(self, filepath='brexport.html'):
```

&nbsp;  
docstring:

```text
This function is used to export a brainrender scene

for hosting it online. It saves an html file that can

be opened in a web browser to show an interactive brainrender scene

```

&nbsp;
## **`keypress`** [#1278]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/scene.py#L1278) online

```python
def keypress(self, key):
```

&nbsp;  
docstring:

no docstring

&nbsp;
## **`take_screenshot`** [#1311]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/scene.py#L1311) online

```python
def take_screenshot(self):
```

&nbsp;  
docstring:

no docstring

&nbsp;

--------
# **DualScene**


```

```

&nbsp;
## **`__init__`** [#1324]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/scene.py#L1324) online

```python
def __init__(self, *args, **kwargs):
```

&nbsp;  
docstring:

no docstring

&nbsp;
## **`render`** [#1327]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/scene.py#L1327) online

```python
def render(self, _interactive=True):
```

&nbsp;  
docstring:

```text

```

&nbsp;
## **`close`** [#1364]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/scene.py#L1364) online

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
## **`__init__`** [#1371]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/scene.py#L1371) online

```python
def __init__(self, N, scenes=None, *args, **kwargs):
```

&nbsp;  
docstring:

no docstring

&nbsp;
## **`render`** [#1384]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/scene.py#L1384) online

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
## **`close`** [#1435]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/scene.py#L1435) online

```python
def close(self):
```

&nbsp;  
docstring:

no docstring