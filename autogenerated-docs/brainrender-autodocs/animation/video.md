# video

## Contents

* [**Video**](video.md#video)
  * [**`__init__`** \[\#19\]](video.md#__init__-19)
  * [**`get_cap_from_images_folder`** \[\#23\]](video.md#get_cap_from_images_folder-23)
  * [**`close`** \[\#46\]](video.md#close-46)
* [**BasicVideoMaker**](video.md#basicvideomaker)
  * [**`__init__`** \[\#79\]](video.md#__init__-79)
  * [**`parse_kwargs`** \[\#95\]](video.md#parse_kwargs-95)
  * [**`make_video`** \[\#115\]](video.md#make_video-115)
* [**CustomVideoMaker**](video.md#customvideomaker)
  * [**`__init__`** \[\#163\]](video.md#__init__-163)
  * [**`make_video`** \[\#166\]](video.md#make_video-166)

## **Video**

### **`__init__`** \[\#19\]

Check the [_**`source code`**_](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/animation/video.py#L19) online

```python
def __init__(self, *args, fmt='mp4', **kwargs):
```

   
docstring:

no docstring

### **`get_cap_from_images_folder`** \[\#23\]

Check the [_**`source code`**_](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/animation/video.py#L23) online

```python
def get_cap_from_images_folder(self, img_format='%1d.png'):
```

   
docstring:

```text
It creates a cv2 VideoCaptur 'cap' from a folder of images (frames)
```

### **`close`** \[\#46\]

Check the [_**`source code`**_](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/animation/video.py#L46) online

```python
def close(self):
```

   
docstring:

```text
Takes a folder full of frames saved as images and converts it into a
    video.
```

## **BasicVideoMaker**

```text
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

### **`__init__`** \[\#79\]

Check the [_**`source code`**_](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/animation/video.py#L79) online

```python
def __init__(self, scene, **kwargs):
```

   
docstring:

no docstring

### **`parse_kwargs`** \[\#95\]

Check the [_**`source code`**_](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/animation/video.py#L95) online

```python
def parse_kwargs(self, **kwargs):
```

   
docstring:

```text
Parses arguments for video creation

Use kwargs to specify:

- save_fld: folder where to save video

- save_name: video name

- video_format: e.g. mp4

- duration: video duration in seconds

- niters: number of iterations (frames) when creating the video

- fps: framerate of video

Arguments not specified in kwargs will be assigned default values
```

### **`make_video`** \[\#115\]

Check the [_**`source code`**_](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/animation/video.py#L115) online

```python
def make_video(self, azimuth=0, elevation=0, roll=0, **kwargs):
```

   
docstring:

```text
Creates a video using user defined parameters

:param azimuth: integer, specify the rotation in degrees per frame on
    the relative axis. (Default value = 0)

:param elevation: integer, specify the rotation in degrees per frame
    on the relative axis. (Default value = 0)

:param roll: integer, specify the rotation in degrees per frame on the
    relative axis. (Default value = 0)

:param kwargs: use to change destination folder, video name, fps,
    duration ... check 'self.parse_kwargs' for details.
```

## **CustomVideoMaker**

```text
Subclasses BasicVideoMaker and replaces make_video method.
```

### **`__init__`** \[\#163\]

Check the [_**`source code`**_](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/animation/video.py#L163) online

```python
def __init__(self, scene, **kwargs):
```

   
docstring:

no docstring

### **`make_video`** \[\#166\]

Check the [_**`source code`**_](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/animation/video.py#L166) online

```python
def make_video(self, video_function, **kwargs):
```

   
docstring:

```text
Let's users use a custom function to create the video.

The custom function must:

- have a 'scene' keyword argument to accept a Scene() instance

- have a 'videomaker' keyword argument to accept the CustomVideoMaker
    (self) instance

- have a 'video' keyword that takes the Video argument

- return the instance of Video

The custom function can manipulate actors and camera in the scene and

add frames to the video with 'video.addFrame()'.

Once all frames are ready it has to return the video object

so that the video can be closed and saved.

:param video_function: custom function used to generate the video's
    frames

see: examples/advanced/custom_videomaker.py
```

