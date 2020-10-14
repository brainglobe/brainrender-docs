



Contents
========

* [**`check_camera_param`** [#55]](#check_camera_param-55)
* [**`buildcam`** [#82]](#buildcam-82)
* [**`set_camera_params`** [#120]](#set_camera_params-120)
* [**`set_camera`** [#129]](#set_camera-129)
* [**`get_camera_params`** [#152]](#get_camera_params-152)


&nbsp;

--------
# **`check_camera_param`** [#55]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/Utils/camera.py#L55) online

```python
def check_camera_param(camera):
```

&nbsp;  
docstring:

no docstring

&nbsp;

--------
# **`buildcam`** [#82]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/Utils/camera.py#L82) online

```python
def buildcam(cm):
```

&nbsp;  
docstring:

```text
Builds a camera from a dictionary of parameters, from vedo

```

&nbsp;

--------
# **`set_camera_params`** [#120]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/Utils/camera.py#L120) online

```python
def set_camera_params(camera, params):
```

&nbsp;  
docstring:

no docstring

&nbsp;

--------
# **`set_camera`** [#129]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/Utils/camera.py#L129) online

```python
def set_camera(scene, camera):
```

&nbsp;  
docstring:

```text
Sets the position of the camera of a brainrender scene.

:param scene: instance of Scene()

:param camera: either a string with the name of one of the available
    cameras, or

a dictionary of camera parameters.

```

&nbsp;

--------
# **`get_camera_params`** [#152]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/Utils/camera.py#L152) online

```python
def get_camera_params(scene=None, camera=None):
```

&nbsp;  
docstring:

```text
Given an active brainrender scene, it return

the camera parameters.

```