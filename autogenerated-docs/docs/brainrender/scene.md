



Contents
========

* [**Scene**](#scene)
* [line: 48 `__init__`](#line-48-__init__)
* [line: 237 `_check_point_in_region`](#line-237-_check_point_in_region)
* [line: 249 `_get_inset`](#line-249-_get_inset)
* [line: 277 `get_n_random_points_in_region`](#line-277-get_n_random_points_in_region)
* [line: 312 `edit_actors`](#line-312-edit_actors)
* [line: 325 `mirror_actor_hemisphere`](#line-325-mirror_actor_hemisphere)
* [line: 338 `cut_actors_with_plane`](#line-338-cut_actors_with_plane)
* [line: 405 `get_cells_in_region`](#line-405-get_cells_in_region)
* [line: 432 `add_root`](#line-432-add_root)
* [line: 456 `add_brain_regions`](#line-456-add_brain_regions)
* [line: 481 `add_neurons`](#line-481-add_neurons)
* [line: 499 `add_neurons_synapses`](#line-499-add_neurons_synapses)
* [line: 514 `add_tractography`](#line-514-add_tractography)
* [line: 524 `add_streamlines`](#line-524-add_streamlines)
* [line: 534 `add_actor`](#line-534-add_actor)
* [line: 558 `add_mesh_silhouette`](#line-558-add_mesh_silhouette)
* [line: 566 `add_from_file`](#line-566-add_from_file)
* [line: 582 `add_sphere_at_point`](#line-582-add_sphere_at_point)
* [line: 600 `add_cells_from_file`](#line-600-add_cells_from_file)
* [line: 664 `add_cells`](#line-664-add_cells)
* [line: 768 `add_optic_cannula`](#line-768-add_optic_cannula)
* [line: 838 `add_text`](#line-838-add_text)
* [line: 857 `add_actor_label`](#line-857-add_actor_label)
* [line: 935 `add_line_at_point`](#line-935-add_line_at_point)
* [line: 958 `add_rostrocaudal_line_at_point`](#line-958-add_rostrocaudal_line_at_point)
* [line: 968 `add_dorsoventral_line_at_point`](#line-968-add_dorsoventral_line_at_point)
* [line: 978 `add_mediolateral_line_at_point`](#line-978-add_mediolateral_line_at_point)
* [line: 988 `add_crosshair_at_point`](#line-988-add_crosshair_at_point)
* [line: 1031 `add_plane`](#line-1031-add_plane)
* [line: 1070 `add_probe_from_sharptrack`](#line-1070-add_probe_from_sharptrack)
* [line: 1138 `apply_render_style`](#line-1138-apply_render_style)
* [line: 1157 `get_actors`](#line-1157-get_actors)
* [line: 1179 `render`](#line-1179-render)
* [line: 1261 `close`](#line-1261-close)
* [line: 1264 `export_for_web`](#line-1264-export_for_web)
* [line: 1310 `keypress`](#line-1310-keypress)
* [line: 1343 `take_screenshot`](#line-1343-take_screenshot)
* [**DualScene**](#dualscene)
* [line: 1356 `__init__`](#line-1356-__init__)
* [line: 1359 `render`](#line-1359-render)
* [line: 1396 `close`](#line-1396-close)
* [**MultiScene**](#multiscene)
* [line: 1403 `__init__`](#line-1403-__init__)
* [line: 1416 `render`](#line-1416-render)
* [line: 1467 `close`](#line-1467-close)


&nbsp;

--------

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

--------
# line: 48 `__init__`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L48) online
#### function definition


```python
def __init__(self, brain_regions=None, regions_aba_color=False, neurons=None, tracts=None, add_root=None, verbose=True, ignore_jupyter=False, display_inset=None, base_dir=None, camera=None, screenshot_kwargs={}, use_default_key_bindings=False, title=None, atlas=None, atlas_kwargs=dict(), **kwargs):
```
##### docstring
  


```python

"""
    Creates and manages a Plotter instance
    
    :param brain_regions: list of brain regions acronyms to be added to the rendered scene (default value None)
    :param regions_aba_color: if True, use the Allen Brain Atlas regions colors (default value None)
    :param neurons: path to JSON or SWC file with data of neurons to be rendered [or list of files] (default value None)
    :param tracts: list of JSON files with tractography data to be rendered (default value None)
    :param add_root: if False a rendered outline of the whole brain is added to the scene (default value None)
    :param verbose: if False less feedback is printed to screen (default value True)
    :param display_insert: if False the inset displaying the brain's outline is not rendered (but the root is added to the scene) (default value None)
    :param base_dir: path to directory to use for saving data (default value None)
    :param camera: name of the camera parameters setting to use (controls the orientation of the rendered scene)
    :param kwargs: can be used to pass path to individual data folders. See brainrender/Utils/paths_manager.py
    :param screenshot_kwargs: pass a dictionary with keys:
                - 'folder' -> str, path to folder where to save screenshots
                - 'name' -> str, filename to prepend to screenshots files
                - 'format' -> str, 'png', 'svg' or 'jpg'
                - scale -> float, values > 1 yield higher resultion screenshots
    :param use_default_key_bindings: if True the defualt keybindings from vedo are used, otherwise
                    a custom function that can be used to take screenshots with the parameter above. 
    :param title: str, if a string is passed a text is added to the top of the rendering window as a title
    :param atlas: str, class. Default None. If a string is passed it whould be the name of a valide
        brainglobe_api atlas. Alternative a class object can be passed, this should support the functionality
        expected of an atlas class. 
        if no atlas is passed the allen brain atlas for the adult mouse brain is used. If a string with the atlas
        name is passed it will try to load the corresponding brainglobe atlas.
    :param atlas_kwargs: dictionary used to pass extra arguments to atlas class
    :param ignore_jupyter: bool, if False brainrender auto-detects if the user is using jupyter and adjusts to it
"""
```

&nbsp;

--------
# line: 237 `_check_point_in_region`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L237) online
#### function definition


```python
def _check_point_in_region(self, point, region_actor):
```
##### docstring
  


```python

"""
    Checks if a point of defined coordinates is within the mesh of a given actorr
    
    :param point: 3-tuple or list of xyz coordinates
    :param region_actor: vedo actor
"""
```

&nbsp;

--------
# line: 249 `_get_inset`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L249) online
#### function definition


```python
def _get_inset(self, **kwargs):
```
##### docstring
  


```python

"""
    Handles the rendering of the inset showing the outline of the whole brain (root) in a corner of the scene.
    
    :param **kwargs:
"""
```

&nbsp;

--------
# line: 277 `get_n_random_points_in_region`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L277) online
#### function definition


```python
def get_n_random_points_in_region(self, region, N, hemisphere=None):
```
##### docstring
  


```python

"""
    Gets N random points inside (or on the surface) of the mesh defining a brain region.
    
    :param region: str, acronym of the brain region.
    :param N: int, number of points to return.
"""
```

&nbsp;

--------
# line: 312 `edit_actors`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L312) online
#### function definition


```python
def edit_actors(self, actors, **kwargs):
```
##### docstring
  


```python

"""
    edits a list of actors (e.g. render as wireframe or solid)
    :param actors: list of actors
    :param **kwargs:
"""
```

&nbsp;

--------
# line: 325 `mirror_actor_hemisphere`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L325) online
#### function definition


```python
def mirror_actor_hemisphere(self, actors):
```
##### docstring
  


```python

"""
    Mirrors actors from one hemisphere to the next
"""
```

&nbsp;

--------
# line: 338 `cut_actors_with_plane`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L338) online
#### function definition


```python
def cut_actors_with_plane(self, plane, actors=None, showplane=False, returncut=False, close_actors=False, **kwargs):
```
##### docstring
  


```python

"""
 no docstring 
"""
```

&nbsp;

--------
# line: 405 `get_cells_in_region`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L405) online
#### function definition


```python
def get_cells_in_region(self, cells, region):
```
##### docstring
  


```python

"""
    Selects the cells that are in a list of user provided regions from a dataframe of cell locations
    
    :param cells: pd.DataFrame of cells x,y,z coordinates
"""
```

&nbsp;

--------
# line: 432 `add_root`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L432) online
#### function definition


```python
def add_root(self, render=True, **kwargs):
```
##### docstring
  


```python

"""
    adds the root the scene (i.e. the whole brain outline)
    
    :param render:  (Default value = True)
    :param **kwargs:
"""
```

&nbsp;

--------
# line: 456 `add_brain_regions`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L456) online
#### function definition


```python
def add_brain_regions(self, *args, **kwargs):
```
##### docstring
  


```python

"""
    Adds brain regions meshes to scene.
    Check the atlas' method to know how it works
"""
```

&nbsp;

--------
# line: 481 `add_neurons`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L481) online
#### function definition


```python
def add_neurons(self, *args, **kwargs):
```
##### docstring
  


```python

"""
    Adds rendered morphological data of neurons reconstructions.
    Check the atlas' method to know how it works
"""
```

&nbsp;

--------
# line: 499 `add_neurons_synapses`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L499) online
#### function definition


```python
def add_neurons_synapses(self, *args, **kwargs):
```
##### docstring
  


```python

"""
    Adds the location of pre or post synapses for a neuron (or list of neurons).
    Check the atlas' method to know how it works. 
"""
```

&nbsp;

--------
# line: 514 `add_tractography`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L514) online
#### function definition


```python
def add_tractography(self, *args, **kwargs):
```
##### docstring
  


```python

"""
    Renders tractography data and adds it to the scene. 
    Check the function definition in ABA for more details
"""
```

&nbsp;

--------
# line: 524 `add_streamlines`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L524) online
#### function definition


```python
def add_streamlines(self, *args, **kwargs):
```
##### docstring
  


```python

"""
    Render streamline data.
    Check the function definition in ABA for more details
"""
```

&nbsp;

--------
# line: 534 `add_actor`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L534) online
#### function definition


```python
def add_actor(self, *actors, store=None):
```
##### docstring
  


```python

"""
    Add a vtk actor to the scene
    
    :param actor:
    :param store: one of the items in self.actors to use to store the actor
            being created. It needs to be a list
"""
```

&nbsp;

--------
# line: 558 `add_mesh_silhouette`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L558) online
#### function definition


```python
def add_mesh_silhouette(self, *actors, lw=1, color='k', **kwargs):
```
##### docstring
  


```python

"""
    Given a list of actors it adds a colored silhouette
    to them.
"""
```

&nbsp;

--------
# line: 566 `add_from_file`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L566) online
#### function definition


```python
def add_from_file(self, *filepaths, **kwargs):
```
##### docstring
  


```python

"""
    Add data to the scene by loading them from a file. Should handle .obj, .vtk and .nii files.
    
    :param filepaths: path to the file. Can pass as many arguments as needed
    :param **kwargs:
"""
```

&nbsp;

--------
# line: 582 `add_sphere_at_point`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L582) online
#### function definition


```python
def add_sphere_at_point(self, pos=[0, 0, 0], radius=100, color='black', alpha=1, **kwargs):
```
##### docstring
  


```python

"""
    Adds a shere at a location specified by the user
    
    :param pos: list of x,y,z coordinates (Default value = [0, 0, 0])
    :param radius: int, radius of the sphere (Default value = 100)
    :param color: color of the sphere (Default value = "black")
    :param alpha: transparency of the sphere (Default value = 1)
    :param **kwargs:
"""
```

&nbsp;

--------
# line: 600 `add_cells_from_file`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L600) online
#### function definition


```python
def add_cells_from_file(self, filepath, hdf_key='hdf', color='red', radius=25, res=3, alpha=1):
```
##### docstring
  


```python

"""
    Load location of cells from a file (csv and HDF) and render as spheres aligned to the root mesh.
    
    :param filepath: str path to file
    :param hdf_key: str (Default value = None)
    :param color: str, color of spheres used to render the cells (Default value = "red")
    :param radius: int, radius of spheres used to render the cells (Default value = 25)
    :param res: int, resolution of spheres used to render the cells (Default value = 3)
    :param alpha: float, transparency of spheres used to render the cells (Default value = 1)
"""
```

&nbsp;

--------
# line: 664 `add_cells`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L664) online
#### function definition


```python
def add_cells(self, coords, color='red', color_by_region=False, color_by_metadata=None, radius=25, res=3, alpha=1, col_names=None, regions=None, verbose=True):
```
##### docstring
  


```python

"""
    Renders cells given their coordinates as a collection of spheres.
    
    :param coords: pandas dataframe with x,y,z coordinates
    :param color: str, color of spheres used to render the cells (Default value = "red"). 
            Alternatively a list of colors specifying the color of each cell.
    :param radius: int, radius of spheres used to render the cells (Default value = 25)
    :param res: int, resolution of spheres used to render the cells (Default value = 3)
    :param alpha: float, transparency of spheres used to render the cells (Default value = 1)
    :param color_by_region: bool. If true the cells are colored according to the color of the brain region they are in
    :param color_by_metadata: str, if the name of a column of the coords dataframe is passed, cells are colored according 
            to their value for that column. If color_by_metadata is passed and a dictionary is passed
            to 'color' at the same time, the dictionary will be used to specify the colors used. Therefore
            `color` should map values in the metadata column to colors
    :param regions: if a list of brain regions acronym is passed, only cells in these regions will be added to the scene
    :param col_names: list of strings with names of pandas dataframe columns. If passed it should be a list of 3 columns
            which have the x, y, z coordinates. If not passed, it is assumed that the columns are ['x', 'y', 'z']
"""
```

&nbsp;

--------
# line: 768 `add_optic_cannula`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L768) online
#### function definition


```python
def add_optic_cannula(self, target_region=None, pos=None, x_offset=0, y_offset=0, z_offset=(- 500), use_line=False, **kwargs):
```
##### docstring
  


```python

"""
    Adds a cylindrical vtk actor to scene to render optic cannulas. By default
    this is a semi-transparent blue cylinder centered on the center of mass of
    a specified target region and oriented vertically.
    
    :param target_region: str, acronym of target region to extract coordinates
        of implanted fiber. By defualt the fiber will be centered on the center
        of mass of the target region but the offset arguments can be used to
        fine tune the position. Alternative pass a 'pos' argument with XYZ coords.
    :param pos: list or tuple or np.array with X,Y,Z coordinates. Must have length = 3.
    :param x_offset, y_offset, z_offset: int, used to fine tune the coordinates of 
        the implanted cannula.
    :param **kwargs: used to specify which hemisphere the cannula is and parameters
        of the rendered cylinder: color, alpha, rotation axis...
"""
```

&nbsp;

--------
# line: 838 `add_text`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L838) online
#### function definition


```python
def add_text(self, text, **kwargs):
```
##### docstring
  


```python

"""
    Adds a 2D text to the scene. Default params are to crate a large black
    text at the top of the rendering window.
    
    :param text: str with text to write
    :param kwargs: keyword arguments accepted by vedo.shapes.Text2D
"""
```

&nbsp;

--------
# line: 857 `add_actor_label`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L857) online
#### function definition


```python
def add_actor_label(self, actors, labels, **kwargs):
```
##### docstring
  


```python

"""
    Adds a 2D text ancored to a point on the actor's mesh
    to label what the actor is
    
    :param kwargs: key word arguments can be passed to determine 
            text appearance and location:
                - size: int, text size. Default 300
                - color: str, text color. A list of colors can be passed
                        if None the actor's color is used. Default None.
                - xoffset, yoffset, zoffset: integers that shift the label position
                - radius: radius of sphere used to denote label anchor. Set to 0 or None to hide. 
"""
```

&nbsp;

--------
# line: 935 `add_line_at_point`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L935) online
#### function definition


```python
def add_line_at_point(self, point, replace_coord, bounds, **kwargs):
```
##### docstring
  


```python

"""
    Adds a line oriented on a given axis at a point
    
    :param point:list or 1d np array with coordinates of point where crosshair is centered
    :param replace_coord: index of the coordinate to replace (i.e. along which axis is the line oriented)
    :param bounds: list of two floats with lower and upper bound for line, determins the extent of the line
    :param kwargs: dictionary with arguments to specify how lines should look like
"""
```

&nbsp;

--------
# line: 958 `add_rostrocaudal_line_at_point`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L958) online
#### function definition


```python
def add_rostrocaudal_line_at_point(self, point, **kwargs):
```
##### docstring
  


```python

"""
    Add a line at a point oriented along the trostrocaudal axis
    
    :param point:list or 1d np array with coordinates of point where crosshair is centered
    :param line_kwargs: dictionary with arguments to specify how lines should look like
"""
```

&nbsp;

--------
# line: 968 `add_dorsoventral_line_at_point`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L968) online
#### function definition


```python
def add_dorsoventral_line_at_point(self, point, **kwargs):
```
##### docstring
  


```python

"""
    Add a line at a point oriented along the mdorsoventralediolateral axis
    
    :param point:list or 1d np array with coordinates of point where crosshair is centered
    :param line_kwargs: dictionary with arguments to specify how lines should look like
"""
```

&nbsp;

--------
# line: 978 `add_mediolateral_line_at_point`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L978) online
#### function definition


```python
def add_mediolateral_line_at_point(self, point, **kwargs):
```
##### docstring
  


```python

"""
    Add a line at a point oriented along the mediolateral axis
    
    :param point:list or 1d np array with coordinates of point where crosshair is centered
    :param line_kwargs: dictionary with arguments to specify how lines should look like
"""
```

&nbsp;

--------
# line: 988 `add_crosshair_at_point`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L988) online
#### function definition


```python
def add_crosshair_at_point(self, point, ml=True, dv=True, ap=True, show_point=True, line_kwargs={}, point_kwargs={}):
```
##### docstring
  


```python

"""
    Add a crosshair (set of orthogonal lines meeting at a point)
    centered on a given point.
    
    :param point: list or 1d np array with coordinates of point where crosshair is centered
    :param ml: bool, if True a line oriented on the mediolateral axis is added
    :param dv: bool, if True a line oriented on the dorsoventral axis is added
    :param ap: bool, if True a line oriented on the anteriorposterior or rostsrocaudal axis is added
    :param show_point: bool, if True a sphere at the loation of the point is shown
    :param line_kwargs: dictionary with arguments to specify how lines should look like
    :param point_kwargs: dictionary with arguments to specify how the point should look
"""
```

&nbsp;

--------
# line: 1031 `add_plane`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L1031) online
#### function definition


```python
def add_plane(self, plane, **kwargs):
```
##### docstring
  


```python

"""
    Adds one or more planes to the scene.
    For more details on how to build custom planes, check:
    brainrender/atlases/base.py -> Base.get_plane_at_point 
    method.
    
    :param plane: either a string with the name of one of 
        the predifined planes ['sagittal', 'coronal', 'horizontal'] 
        or an instance of the Plane class from vedo.shapes
"""
```

&nbsp;

--------
# line: 1070 `add_probe_from_sharptrack`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L1070) online
#### function definition


```python
def add_probe_from_sharptrack(self, probe_points_file, points_kwargs={}, **kwargs):
```
##### docstring
  


```python

"""
    Visualises the position of an implanted probe in the brain. 
    Uses the location of points along the probe extracted with SharpTrack
    [https://github.com/cortex-lab/allenCCF].
    It renders the position of points along the probe and a line fit through them.
    Code contributed by @tbslv on github. 
    
    :param probe_points_file: str, path to a .mat file with probe points coordinates
    :param points_kwargs: dict, used to specify how probe points should look like (e.g color, alpha...)
    :param kwargs: keyword arguments used to specify how the probe should look like (e.g. color, alpha...)
"""
```

&nbsp;

--------
# line: 1138 `apply_render_style`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L1138) online
#### function definition


```python
def apply_render_style(self):
```
##### docstring
  


```python

"""
 no docstring 
"""
```

&nbsp;

--------
# line: 1157 `get_actors`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L1157) online
#### function definition


```python
def get_actors(self):
```
##### docstring
  


```python

"""
 no docstring 
"""
```

&nbsp;

--------
# line: 1179 `render`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L1179) online
#### function definition


```python
def render(self, interactive=True, video=False, camera=None, zoom=None, **kwargs):
```
##### docstring
  


```python

"""
    Takes care of rendering the scene
"""
```

&nbsp;

--------
# line: 1261 `close`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L1261) online
#### function definition


```python
def close(self):
```
##### docstring
  


```python

"""
 no docstring 
"""
```

&nbsp;

--------
# line: 1264 `export_for_web`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L1264) online
#### function definition


```python
def export_for_web(self, filepath='brexport.html'):
```
##### docstring
  


```python

"""
    This function is used to export a brainrender scene
    for hosting it online. It saves an html file that can
    be opened in a web browser to show an interactive brainrender scene
"""
```

&nbsp;

--------
# line: 1310 `keypress`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L1310) online
#### function definition


```python
def keypress(self, key):
```
##### docstring
  


```python

"""
 no docstring 
"""
```

&nbsp;

--------
# line: 1343 `take_screenshot`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L1343) online
#### function definition


```python
def take_screenshot(self):
```
##### docstring
  


```python

"""
 no docstring 
"""
```

&nbsp;

--------

--------
# **DualScene**


```

```

&nbsp;

--------
# line: 1356 `__init__`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L1356) online
#### function definition


```python
def __init__(self, *args, **kwargs):
```
##### docstring
  


```python

"""
 no docstring 
"""
```

&nbsp;

--------
# line: 1359 `render`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L1359) online
#### function definition


```python
def render(self, _interactive=True):
```
##### docstring
  


```python

"""
    
"""
```

&nbsp;

--------
# line: 1396 `close`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L1396) online
#### function definition


```python
def close(self):
```
##### docstring
  


```python

"""
 no docstring 
"""
```

&nbsp;

--------

--------
# **MultiScene**


```

```

&nbsp;

--------
# line: 1403 `__init__`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L1403) online
#### function definition


```python
def __init__(self, N, scenes=None, *args, **kwargs):
```
##### docstring
  


```python

"""
 no docstring 
"""
```

&nbsp;

--------
# line: 1416 `render`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L1416) online
#### function definition


```python
def render(self, _interactive=True, **kwargs):
```
##### docstring
  


```python

"""
    :param _interactive:  (Default value = True)
    :param **kwargs:
"""
```

&nbsp;

--------
# line: 1467 `close`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/scene.py#L1467) online
#### function definition


```python
def close(self):
```
##### docstring
  


```python

"""
 no docstring 
"""
```