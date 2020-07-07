



Contents
========

* [**Base**](#base)
	* [line: 18 - `__init__`](#line-18---__init__)
	* [line: 26 - `get_plane_at_point`](#line-26---get_plane_at_point)
	* [line: 42 - `get_sagittal_plane`](#line-42---get_sagittal_plane)
	* [line: 69 - `get_horizontal_plane`](#line-69---get_horizontal_plane)
	* [line: 96 - `get_coronal_plane`](#line-96---get_coronal_plane)
	* [line: 124 - `get_region_CenterOfMass`](#line-124---get_region_centerofmass)
	* [line: 167 - `_get_structure_mesh`](#line-167---_get_structure_mesh)
	* [line: 171 - `get_brain_regions`](#line-171---get_brain_regions)
	* [line: 286 - `get_structure_ancestors`](#line-286---get_structure_ancestors)
	* [line: 328 - `get_structure_descendants`](#line-328---get_structure_descendants)
	* [line: 333 - `get_structure_parent`](#line-333---get_structure_parent)
	* [line: 359 - `get_region_unilateral`](#line-359---get_region_unilateral)
	* [line: 398 - `mirror_point_across_hemispheres`](#line-398---mirror_point_across_hemispheres)
	* [line: 403 - `get_colors_from_coordinates`](#line-403---get_colors_from_coordinates)


&nbsp;

--------

--------
# **Base**




--------
## line: 18 - `__init__`
  
```  
def __init__(self):
```


>  no docstring

--------
## line: 26 - `get_plane_at_point`
  
```  
def get_plane_at_point(self, pos, norm, sx, sy, color='lightgray', alpha=0.25, **kwargs):
```
>Returns a plane going through a point at pos, oriented orthogonally to the vector norm and of width and heightsx, sy.   
:param pos: 3-tuple or list with x,y,z, coords of point the plane goes through  
:param sx, sy: int, width and height of the plane  
:param norm: 3-tuple or list with 3d vector the plane is orthogonal to  
:param color, alpha: plane color and transparency

--------
## line: 42 - `get_sagittal_plane`
  
```  
def get_sagittal_plane(self, pos=None, **kwargs):
```
>Creates a Plane actor centered at the midpoint of root (or a user given locatin)and oriented along the sagittal axis  
:param pos: if not None, passe a list of 3 xyz defining the position of the                 point the plane goes through.

--------
## line: 69 - `get_horizontal_plane`
  
```  
def get_horizontal_plane(self, pos=None, **kwargs):
```
>Creates a Plane actor centered at the midpoint of root (or a user given locatin)and oriented along the horizontal axis  
:param pos: if not None, passe a list of 3 xyz defining the position of the                 point the plane goes through.

--------
## line: 96 - `get_coronal_plane`
  
```  
def get_coronal_plane(self, pos=None, **kwargs):
```
>Creates a Plane actor centered at the midpoint of root (or a user given locatin)and oriented along the coronal axis  
:param pos: if not None, passe a list of 3 xyz defining the position of the                 point the plane goes through.

--------
## line: 124 - `get_region_CenterOfMass`
  
```  
def get_region_CenterOfMass(self, regions, unilateral=True, hemisphere='right'):
```
>Get the center of mass of the 3d mesh of one or multiple brain regions.  
:param regions: str, list of brain regions acronyms  
:param unilateral: bool, if True, the CoM is relative to one hemisphere (Default value = True)  
:param hemisphere: str, if unilteral=True, specifies which hemisphere to use ['left' or 'right'] (Default value = "right"):returns: coms = {list, dict} -- [if only one regions is passed, then just returns the CoM coordinates for that region.                        If a list is passed then a dictionary is returned. ]

--------
## line: 167 - `_get_structure_mesh`
  
```  
def _get_structure_mesh(self, acronym, **kwargs):
```


>  no docstring

--------
## line: 171 - `get_brain_regions`
  
```  
def get_brain_regions(self, brain_regions, add_labels=False, colors=None, use_original_color=True, alpha=None, hemisphere=None, verbose=False, **kwargs):
```
>Gets brain regions meshes for renderingMany parameters can be passed to specify how the regions should be rendered.To treat a subset of the rendered regions, specify which regions are VIP. Use the kwargs to specify more detailes on how the regins should be rendered (e.g. wireframe look)  
:param brain_regions: str list of acronyms of brain regions  
:param colors: str, color of rendered brian regions (Default value = None)  
:param use_original_color: bool, if True, the allen's default color for the region is used.  (Default value = False)  
:param alpha: float, transparency of the rendered brain regions (Default value = None)  
:param hemisphere: str (Default value = None)  
:param add_labels: bool (default False). If true a label is added to each regions' actor. The label is visible when hovering the mouse over the actor  
:param **kwargs: used to determine a bunch of thigs, including the look and location of lables from scene.add_labels

--------
## line: 286 - `get_structure_ancestors`
  
```  
def get_structure_ancestors(self, regions, ancestors=True, descendants=False):
```
>Get's the ancestors of the region(s) passed as arguments  
:param regions: str, list of str with acronums of regions of interest  
:param ancestors: if True, returns the ancestors of the region  (Default value = True)  
:param descendants: if True, returns the descendants of the region (Default value = False)

--------
## line: 328 - `get_structure_descendants`
  
```  
def get_structure_descendants(self, regions):
```


>  no docstring

--------
## line: 333 - `get_structure_parent`
  
```  
def get_structure_parent(self, acronyms):
```
>Gets the parent of a brain region (or list of regions) from the hierarchical structure of theAllen Brain Atals.  
:param acronyms: list of acronyms of brain regions.

--------
## line: 359 - `get_region_unilateral`
  
```  
def get_region_unilateral(self, region, hemisphere='both', color=None, alpha=None):
```
>Regions meshes are loaded with both hemispheres' meshes by default.This function splits them in two.  
:param region: str, actors of brain region  
:param hemisphere: str, which hemisphere to return ['left', 'right' or 'both'] (Default value = "both")  
:param color: color of each side's mesh. (Default value = None)  
:param alpha: transparency of each side's mesh.  (Default value = None)

--------
## line: 398 - `mirror_point_across_hemispheres`
  
```  
def mirror_point_across_hemispheres(self, point):
```


>  no docstring

--------
## line: 403 - `get_colors_from_coordinates`
  
```  
def get_colors_from_coordinates(self, p0):
```
>Given a point or a list of points returns a list of colors whereeach item is the color of the brain region each point is in