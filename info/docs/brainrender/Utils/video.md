



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
  
```  
def cap_set_frame(cap, frame_number):
```
>Sets an opencv video capture object to a specific frame

&nbsp;

--------
# line: 22 - `get_cap_selected_frame`
  
```  
def get_cap_selected_frame(cap, show_frame):
```
>Gets a frame from an opencv video capture object to a specific frame

&nbsp;

--------
# line: 35 - `get_video_params`
  
```  
def get_video_params(cap):
```
>Gets video parameters from an opencv video capture object

&nbsp;

--------
# line: 56 - `open_cvwriter`
  
```  
def open_cvwriter(filepath, w=None, h=None, framerate=None, format='.mp4', iscolor=False):
```
>Creats an instance of cv.VideoWriter to write frames to video using python opencv  
:param filepath: str, path to file to save  
:param w,h: width and height of frame in pixels  
:param framerate: fps of output video  
:param format: video format  
:param iscolor: bool, set as true if images are rgb, else false if they are gray

&nbsp;

--------
# line: 81 - `save_videocap_to_video`
  
```  
def save_videocap_to_video(cap, savepath, fmt, fps=30, iscolor=True):
```
>Saves the content of a videocapture opencv object to a file