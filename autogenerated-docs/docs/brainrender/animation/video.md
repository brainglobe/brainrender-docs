



Contents
========

* [**Video**](#video)
* [line: 19 `__init__`](#line-19-__init__)
* [line: 23 `get_cap_from_images_folder`](#line-23-get_cap_from_images_folder)
* [line: 46 `close`](#line-46-close)
* [**BasicVideoMaker**](#basicvideomaker)
* [line: 79 `__init__`](#line-79-__init__)
* [line: 95 `parse_kwargs`](#line-95-parse_kwargs)
* [line: 115 `make_video`](#line-115-make_video)
* [**CustomVideoMaker**](#customvideomaker)
* [line: 163 `__init__`](#line-163-__init__)
* [line: 166 `make_video`](#line-166-make_video)


&nbsp;

--------

--------
# **Video**




&nbsp;

--------
# line: 19 `__init__`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/animation/video.py#L19) online
#### function definition


```python
def __init__(self, *args, fmt='mp4', **kwargs):
```
##### docstring
  


```python

"""
 no docstring 
"""
```

&nbsp;

--------
# line: 23 `get_cap_from_images_folder`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/animation/video.py#L23) online
#### function definition


```python
def get_cap_from_images_folder(self, img_format='%1d.png'):
```
##### docstring
  


```python

"""
    It creates a cv2 VideoCaptur 'cap' from a folder of images (frames)
"""
```

&nbsp;

--------
# line: 46 `close`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/animation/video.py#L46) online
#### function definition


```python
def close(self):
```
##### docstring
  


```python

"""
    Takes a folder full of frames saved as images and converts it into a video.
"""
```

&nbsp;

--------

--------
# **BasicVideoMaker**


```
Wrapper around vedo Video class to facilitate the creation of videos from
brainrender scenes.

Use kwargs to specify:
    - save_fld: folder where to save video
    - save_name: video name
    - video_format: e.g. mp4
    - duration: video duration in seconds
    - niters: number of iterations (frames) when creating the video
    - fps: framerate of video
```

&nbsp;

--------
# line: 79 `__init__`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/animation/video.py#L79) online
#### function definition


```python
def __init__(self, scene, **kwargs):
```
##### docstring
  


```python

"""
 no docstring 
"""
```

&nbsp;

--------
# line: 95 `parse_kwargs`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/animation/video.py#L95) online
#### function definition


```python
def parse_kwargs(self, **kwargs):
```
##### docstring
  


```python

"""
    Parses arguments for video creation
    Use kwargs to specify:
        - save_fld: folder where to save video
        - save_name: video name
        - video_format: e.g. mp4
        - duration: video duration in seconds
        - niters: number of iterations (frames) when creating the video
        - fps: framerate of video
    
    Arguments not specified in kwargs will be assigned default values
"""
```

&nbsp;

--------
# line: 115 `make_video`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/animation/video.py#L115) online
#### function definition


```python
def make_video(self, azimuth=0, elevation=0, roll=0, **kwargs):
```
##### docstring
  


```python

"""
    Creates a video using user defined parameters
    
    :param azimuth: integer, specify the rotation in degrees per frame on the relative axis. (Default value = 0)
    :param elevation: integer, specify the rotation in degrees per frame on the relative axis. (Default value = 0)
    :param roll: integer, specify the rotation in degrees per frame on the relative axis. (Default value = 0)
    :param kwargs: use to change destination folder, video name, fps, duration ... check 'self.parse_kwargs' for details. 
"""
```

&nbsp;

--------

--------
# **CustomVideoMaker**


```
Subclasses BasicVideoMaker and replaces make_video method.
```

&nbsp;

--------
# line: 163 `__init__`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/animation/video.py#L163) online
#### function definition


```python
def __init__(self, scene, **kwargs):
```
##### docstring
  


```python

"""
 no docstring 
"""
```

&nbsp;

--------
# line: 166 `make_video`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/animation/video.py#L166) online
#### function definition


```python
def make_video(self, video_function, **kwargs):
```
##### docstring
  


```python

"""
    Let's users use a custom function to create the video.
    The custom function must:
        - have a 'scene' keyword argument to accept a Scene() instance
        - have a 'videomaker' keyword argument to accept the CustomVideoMaker (self) instance
        - have a 'video' keyword that takes the Video argument
        - return the instance of Video
    
    The custom function can manipulate actors and camera in the scene and 
    add frames to the video with 'video.addFrame()'. 
    Once all frames are ready it has to return the video object 
    so that the video can be closed and saved.     
    
    :param video_function: custom function used to generate the video's frames
    
    see: examples/advanced/custom_videomaker.py
"""
```