# camera

## Contents

* [line: 44 - `check_camera_param`](camera.md#line-44---check_camera_param)
* [line: 70 - `buildcam`](camera.md#line-70---buildcam)
* [line: 108 - `set_camera_params`](camera.md#line-108---set_camera_params)
* [line: 117 - `set_camera`](camera.md#line-117---set_camera)
* [line: 140 - `get_camera_params`](camera.md#line-140---get_camera_params)

## line: 44 - `check_camera_param`

```text
def check_camera_param(camera):
```

> no docstring

## line: 70 - `buildcam`

```text
def buildcam(cm):
```

> Builds a camera from a dictionary of parameters, from vedo

## line: 108 - `set_camera_params`

```text
def set_camera_params(camera, params):
```

> no docstring

## line: 117 - `set_camera`

```text
def set_camera(scene, camera):
```

> Sets the position of the camera of a brainrender scene.  
> :param scene: instance of Scene\(\)  
> :param camera: either a string with the name of one of the available cameras, or a dictionary of camera parameters.

## line: 140 - `get_camera_params`

```text
def get_camera_params(scene=None, camera=None):
```

> Given an active brainrender scene, it returnthe camera parameters.

