# volume

## Contents

* [**`load_labelled_volume`** \[\#9\]](volume.md#load_labelled_volume-9)
* [**`extract_volume_surface`** \[\#40\]](volume.md#extract_volume_surface-40)
* [**`extract_label_mesh`** \[\#62\]](volume.md#extract_label_mesh-62)

## **`load_labelled_volume`** \[\#9\]

Check the [_**`source code`**_](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/Utils/volume.py#L9) online

```python
def load_labelled_volume(data, vmin=0, alpha=1, **kwargs):
```

   
docstring:

```text
Load volume image from .nrrd file.

It assume that voxels with value = 0 are empty while voxels with
    values > 0

are labelles (e.g. to indicate the location of a brain region in a
    reference atlas)

:param data: str, path to file with volume data or 3d numpy array

:param vmin: float, values below this numner will be assigned an
    alpha=0 and not be visualized

:param **kwargs: kwargs to pass to the Volume class from vedo

:param alpha: float in range [0, 1], transparency [for the part of
    volume with value > vmin]
```

## **`extract_volume_surface`** \[\#40\]

Check the [_**`source code`**_](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/Utils/volume.py#L40) online

```python
def extract_volume_surface(vol, threshold=0.1, smooth=False):
```

   
docstring:

```text
Returns a vedo mesh actor with just the outer surface of a volume

:param vol: instance of Volume class from vedo

:param threshold: float, min value to threshold the volume for
    isosurface extraction

:param smooth: bool, if True the surface mesh is smoothed
```

## **`extract_label_mesh`** \[\#62\]

Check the [_**`source code`**_](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/Utils/volume.py#L62) online

```python
def extract_label_mesh(vol, lbl):
```

   
docstring:

```text
Given a vedo Volume with a scalar value labelling each voxel,

this function returns a mesh of only the voxels whose value matches
    the lbl argument

:param vol: a vedo Volume

:param lbl: float or int
```

