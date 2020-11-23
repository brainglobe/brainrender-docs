# camera

## Contents

* [**`check_camera_param`** \[\#44\]](camera.md#check_camera_param-44)
* [**`buildcam`** \[\#70\]](camera.md#buildcam-70)
* [**`set_camera_params`** \[\#108\]](camera.md#set_camera_params-108)
* [**`set_camera`** \[\#117\]](camera.md#set_camera-117)
* [**`get_camera_params`** \[\#140\]](camera.md#get_camera_params-140)

## **`check_camera_param`** \[\#44\]

Check the [_**`source code`**_](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/Utils/camera.py#L44) online

```python
def check_camera_param(camera):
```

   
docstring:

no docstring

## **`buildcam`** \[\#70\]

Check the [_**`source code`**_](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/Utils/camera.py#L70) online

```python
def buildcam(cm):
```

   
docstring:

```text
Builds a camera from a dictionary of parameters, from vedo
```

## **`set_camera_params`** \[\#108\]

Check the [_**`source code`**_](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/Utils/camera.py#L108) online

```python
def set_camera_params(camera, params):
```

   
docstring:

no docstring

## **`set_camera`** \[\#117\]

Check the [_**`source code`**_](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/Utils/camera.py#L117) online

```python
def set_camera(scene, camera):
```

   
docstring:

```text
Sets the position of the camera of a brainrender scene.

:param scene: instance of Scene()

:param camera: either a string with the name of one of the available
    cameras, or

a dictionary of camera parameters.
```

## **`get_camera_params`** \[\#140\]

Check the [_**`source code`**_](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/Utils/camera.py#L140) online

```python
def get_camera_params(scene=None, camera=None):
```

   
docstring:

```text
Given an active brainrender scene, it return

the camera parameters.
```

