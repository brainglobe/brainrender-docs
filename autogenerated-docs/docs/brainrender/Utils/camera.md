



Contents
========

* [**`check_camera_param`**  [#44]](#check_camera_param--44)
* [**`buildcam`**  [#70]](#buildcam--70)
* [**`set_camera_params`**  [#108]](#set_camera_params--108)
* [**`set_camera`**  [#117]](#set_camera--117)
* [**`get_camera_params`**  [#140]](#get_camera_params--140)


&nbsp;

--------
# **`check_camera_param`**  [#44]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/Utils/camera.py#L44) online

```python
def check_camera_param(camera):
```  


no docstring

&nbsp;

--------
# **`buildcam`**  [#70]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/Utils/camera.py#L70) online

```python
def buildcam(cm):
```  


```text
Builds a camera from a dictionary of parameters, from vedo

```

&nbsp;

--------
# **`set_camera_params`**  [#108]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/Utils/camera.py#L108) online

```python
def set_camera_params(camera, params):
```  


no docstring

&nbsp;

--------
# **`set_camera`**  [#117]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/Utils/camera.py#L117) online

```python
def set_camera(scene, camera):
```  


```text
Sets the position of the camera of a brainrender scene. 
:param scene: instance of scene()
:param camera: either a string with the name of one of the available cameras, or
a dictionary of camera parameters.  

```

&nbsp;

--------
# **`get_camera_params`**  [#140]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/Utils/camera.py#L140) online

```python
def get_camera_params(scene=None, camera=None):
```  


```text
Given an active brainrender scene, it return
the camera parameters.  

```