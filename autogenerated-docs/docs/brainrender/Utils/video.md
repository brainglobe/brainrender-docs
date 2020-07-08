



Contents
========

* [line: 15 - `cap_set_frame`](#line-15---cap_set_frame)
* [line: 22 - `get_cap_selected_frame`](#line-22---get_cap_selected_frame)
* [line: 35 - `get_video_params`](#line-35---get_video_params)
* [line: 56 - `open_cvwriter`](#line-56---open_cvwriter)
* [line: 81 - `save_videocap_to_video`](#line-81---save_videocap_to_video)


&nbsp;

--------
# line: 15 - `cap_set_frame`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/Utils/video.py#L15) online
#### function definition


```python
def cap_set_frame(cap, frame_number):
```
##### docstring
  


```python

"""
    Sets an opencv video capture object to a specific frame
"""
```

&nbsp;

--------
# line: 22 - `get_cap_selected_frame`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/Utils/video.py#L22) online
#### function definition


```python
def get_cap_selected_frame(cap, show_frame):
```
##### docstring
  


```python

"""
    Gets a frame from an opencv video capture object to a specific frame
"""
```

&nbsp;

--------
# line: 35 - `get_video_params`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/Utils/video.py#L35) online
#### function definition


```python
def get_video_params(cap):
```
##### docstring
  


```python

"""
    Gets video parameters from an opencv video capture object
"""
```

&nbsp;

--------
# line: 56 - `open_cvwriter`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/Utils/video.py#L56) online
#### function definition


```python
def open_cvwriter(filepath, w=None, h=None, framerate=None, format='.mp4', iscolor=False):
```
##### docstring
  


```python

"""
    Creats an instance of cv.VideoWriter to write frames to video using python opencv
    :param filepath: str, path to file to save
    :param w,h: width and height of frame in pixels
    :param framerate: fps of output video
    :param format: video format
    :param iscolor: bool, set as true if images are rgb, else false if they are gray
"""
```

&nbsp;

--------
# line: 81 - `save_videocap_to_video`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/Utils/video.py#L81) online
#### function definition


```python
def save_videocap_to_video(cap, savepath, fmt, fps=30, iscolor=True):
```
##### docstring
  


```python

"""
    Saves the content of a videocapture opencv object to a file
"""
```