



Contents
========

* [line: 44 - `check_camera_param`](#line-44---check_camera_param)
* [line: 70 - `buildcam`](#line-70---buildcam)
* [line: 108 - `set_camera_params`](#line-108---set_camera_params)
* [line: 117 - `set_camera`](#line-117---set_camera)
* [line: 140 - `get_camera_params`](#line-140---get_camera_params)


&nbsp;

--------
# line: 44 - `check_camera_param`
  
```  
def check_camera_param(camera):
```


>  no docstring

&nbsp;

--------
# line: 70 - `buildcam`
  
```  
def buildcam(cm):
```
>Builds a camera from a dictionary of parameters, from vedo

&nbsp;

--------
# line: 108 - `set_camera_params`
  
```  
def set_camera_params(camera, params):
```


>  no docstring

&nbsp;

--------
# line: 117 - `set_camera`
  
```  
def set_camera(scene, camera):
```
>Sets the position of the camera of a brainrender scene.  
:param scene: instance of Scene()  
:param camera: either a string with the name of one of the available cameras, or                a dictionary of camera parameters. 

&nbsp;

--------
# line: 140 - `get_camera_params`
  
```  
def get_camera_params(scene=None, camera=None):
```
>Given an active brainrender scene, it returnthe camera parameters. 