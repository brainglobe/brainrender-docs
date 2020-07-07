



Contents
========

* [**Video**](#video)
	* [line: 19 - `__init__`](#line-19---__init__)
	* [line: 23 - `get_cap_from_images_folder`](#line-23---get_cap_from_images_folder)
	* [line: 46 - `close`](#line-46---close)
* [**BasicVideoMaker**](#basicvideomaker)
	* [line: 79 - `__init__`](#line-79---__init__)
	* [line: 95 - `parse_kwargs`](#line-95---parse_kwargs)
	* [line: 115 - `make_video`](#line-115---make_video)
* [**CustomVideoMaker**](#customvideomaker)
	* [line: 163 - `__init__`](#line-163---__init__)
	* [line: 166 - `make_video`](#line-166---make_video)


&nbsp;

--------

--------
# **Video**




--------
## line: 19 - `__init__`
  
```  
def __init__(self, *args, fmt='mp4', **kwargs):
```


>  no docstring

--------
## line: 23 - `get_cap_from_images_folder`
  
```  
def get_cap_from_images_folder(self, img_format='%1d.png'):
```
>It creates a cv2 VideoCaptur 'cap' from a folder of images (frames)

--------
## line: 46 - `close`
  
```  
def close(self):
```
>Takes a folder full of frames saved as images and converts it into a video.

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

--------
## line: 79 - `__init__`
  
```  
def __init__(self, scene, **kwargs):
```


>  no docstring

--------
## line: 95 - `parse_kwargs`
  
```  
def parse_kwargs(self, **kwargs):
```
>Parses arguments for video creationUse kwargs to specify:    - save_fld: folder where to save video    - save_name: video name    - video_format: e.g. mp4    - duration: video duration in seconds    - niters: number of iterations (frames) when creating the video    - fps: framerate of videoArguments not specified in kwargs will be assigned default values

--------
## line: 115 - `make_video`
  
```  
def make_video(self, azimuth=0, elevation=0, roll=0, **kwargs):
```
>Creates a video using user defined parameters  
:param azimuth: integer, specify the rotation in degrees per frame on the relative axis. (Default value = 0)  
:param elevation: integer, specify the rotation in degrees per frame on the relative axis. (Default value = 0)  
:param roll: integer, specify the rotation in degrees per frame on the relative axis. (Default value = 0)  
:param kwargs: use to change destination folder, video name, fps, duration ... check 'self.parse_kwargs' for details. 

&nbsp;

--------

--------
# **CustomVideoMaker**
  
```  
Subclasses BasicVideoMaker and replaces make_video method.  
```

--------
## line: 163 - `__init__`
  
```  
def __init__(self, scene, **kwargs):
```


>  no docstring

--------
## line: 166 - `make_video`
  
```  
def make_video(self, video_function, **kwargs):
```
>Let's users use a custom function to create the video.The custom function must:    - have a 'scene' keyword argument to accept a Scene() instance    - have a 'videomaker' keyword argument to accept the CustomVideoMaker (self) instance    - have a 'video' keyword that takes the Video argument    - return the instance of VideoThe custom function can manipulate actors and camera in the scene and add frames to the video with 'video.addFrame()'. Once all frames are ready it has to return the video object so that the video can be closed and saved.       
:param video_function: custom function used to generate the video's framessee: examples/advanced/custom_videomaker.py