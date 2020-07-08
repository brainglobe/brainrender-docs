



Contents
========

* [line: 44 `check_camera_param`](#line-44-check_camera_param)
* [line: 70 `buildcam`](#line-70-buildcam)
* [line: 108 `set_camera_params`](#line-108-set_camera_params)
* [line: 117 `set_camera`](#line-117-set_camera)
* [line: 140 `get_camera_params`](#line-140-get_camera_params)


&nbsp;

--------
# line: 44 `check_camera_param`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/Utils/camera.py#L44) online
#### function definition


```python
def check_camera_param(camera):
```
##### docstring
  


```python

"""
 no docstring 
"""
```

&nbsp;

--------
# line: 70 `buildcam`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/Utils/camera.py#L70) online
#### function definition


```python
def buildcam(cm):
```
##### docstring
  


```python

"""
    Builds a camera from a dictionary of parameters, from vedo
"""
```

&nbsp;

--------
# line: 108 `set_camera_params`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/Utils/camera.py#L108) online
#### function definition


```python
def set_camera_params(camera, params):
```
##### docstring
  


```python

"""
 no docstring 
"""
```

&nbsp;

--------
# line: 117 `set_camera`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/Utils/camera.py#L117) online
#### function definition


```python
def set_camera(scene, camera):
```
##### docstring
  


```python

"""
    Sets the position of the camera of a brainrender scene.
    
    :param scene: instance of Scene()
    :param camera: either a string with the name of one of the available cameras, or
                    a dictionary of camera parameters. 
"""
```

&nbsp;

--------
# line: 140 `get_camera_params`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/Utils/camera.py#L140) online
#### function definition


```python
def get_camera_params(scene=None, camera=None):
```
##### docstring
  


```python

"""
    Given an active brainrender scene, it return
    the camera parameters. 
"""
```