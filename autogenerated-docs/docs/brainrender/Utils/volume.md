



Contents
========

* [**`load_labelled_volume`** [#9]](#load_labelled_volume-9)
* [**`extract_volume_surface`** [#40]](#extract_volume_surface-40)
* [**`extract_label_mesh`** [#62]](#extract_label_mesh-62)


&nbsp;

--------
# **`load_labelled_volume`** [#9]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/Utils/volume.py#L9) online

```python
def load_labelled_volume(data, vmin=0, alpha=1, **kwargs):
```  


```text
Load volume image from . Nrrd file.
it assume that voxels with value = 0 are empty while voxels with
    values > 0
are labelles (e. G.  to indicate the location of a brain region in a
    reference atlas)
:param data: str, path to file with volume data or 3d numpy array
:param vmin: float, values below this numner will be assigned an
    alpha=0 and not be visualized
:param **kwargs: kwargs to pass to the volume class from vedo
:param alpha: float in range [0, 1], transparency [for the part of
    volume with value > vmin]
```

&nbsp;

--------
# **`extract_volume_surface`** [#40]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/Utils/volume.py#L40) online

```python
def extract_volume_surface(vol, threshold=0.1, smooth=False):
```  


```text
Returns a vedo mesh actor with just the outer surface of a volume
:param vol: instance of volume class from vedo
:param threshold: float, min value to threshold the volume for
    isosurface extraction
:param smooth: bool, if true the surface mesh is smoothed
```

&nbsp;

--------
# **`extract_label_mesh`** [#62]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/Utils/volume.py#L62) online

```python
def extract_label_mesh(vol, lbl):
```  


```text
Given a vedo volume with a scalar value labelling each voxel,
this function returns a mesh of only the voxels whose value matches
    the lbl argument
:param vol: a vedo volume
:param lbl: float or int
```