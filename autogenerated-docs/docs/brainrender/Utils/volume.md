



Contents
========

* [line: 9 - `load_labelled_volume`](#line-9---load_labelled_volume)
* [line: 40 - `extract_volume_surface`](#line-40---extract_volume_surface)
* [line: 62 - `extract_label_mesh`](#line-62---extract_label_mesh)


&nbsp;

--------
# line: 9 - `load_labelled_volume`
  
```  
def load_labelled_volume(data, vmin=0, alpha=1, **kwargs):
```
>Load volume image from .nrrd file. It assume that voxels with value = 0 are empty while voxels with values > 0are labelles (e.g. to indicate the location of a brain region in a reference atlas)  
:param data: str, path to file with volume data or 3d numpy array  
:param vmin: float, values below this numner will be assigned an alpha=0 and not be visualized  
:param **kwargs: kwargs to pass to the Volume class from vedo  
:param alpha: float in range [0, 1], transparency [for the part of volume with value > vmin]

&nbsp;

--------
# line: 40 - `extract_volume_surface`
  
```  
def extract_volume_surface(vol, threshold=0.1, smooth=False):
```
>Returns a vedo mesh actor with just the outer surface of a volume  
:param vol: instance of Volume class from vedo  
:param threshold: float, min value to threshold the volume for isosurface extraction  
:param smooth: bool, if True the surface mesh is smoothed

&nbsp;

--------
# line: 62 - `extract_label_mesh`
  
```  
def extract_label_mesh(vol, lbl):
```
>Given a vedo Volume with a scalar value labelling each voxel, this function returns a mesh of only the voxels whose value matches the lbl argument  
:param vol: a vedo Volume  
:param lbl: float or int