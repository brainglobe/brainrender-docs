



Contents
========

* [line: 15 `listdir`](#line-15-listdir)
* [line: 28 `get_subdirs`](#line-28-get_subdirs)
* [line: 35 `check_file_exists`](#line-35-check_file_exists)
* [line: 45 `get_file_name`](#line-45-get_file_name)
* [line: 51 `load_npy_from_gz`](#line-51-load_npy_from_gz)
* [line: 56 `save_npy_to_gz`](#line-56-save_npy_to_gz)
* [line: 62 `save_json`](#line-62-save_json)
* [line: 81 `save_yaml`](#line-81-save_yaml)
* [line: 103 `load_json`](#line-103-load_json)
* [line: 117 `load_yaml`](#line-117-load_yaml)
* [line: 131 `load_volume_file`](#line-131-load_volume_file)
* [line: 149 `load_mesh_from_file`](#line-149-load_mesh_from_file)
* [line: 180 `connected_to_internet`](#line-180-connected_to_internet)
* [line: 196 `send_query`](#line-196-send_query)
* [line: 215 `get_probe_points_from_sharptrack`](#line-215-get_probe_points_from_sharptrack)


&nbsp;

--------
# line: 15 `listdir`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/Utils/data_io.py#L15) online
#### function definition


```python
def listdir(fld):
```
##### docstring
  


```python

"""
    List the files into a folder with the coplete file path instead of the relative file path like os.listdir.
    
    :param fld: string, folder path
"""
```

&nbsp;

--------
# line: 28 `get_subdirs`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/Utils/data_io.py#L28) online
#### function definition


```python
def get_subdirs(folderpath):
```
##### docstring
  


```python

"""
    Returns the subfolders in a given folder
"""
```

&nbsp;

--------
# line: 35 `check_file_exists`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/Utils/data_io.py#L35) online
#### function definition


```python
def check_file_exists(filepath, raise_error=False):
```
##### docstring
  


```python

"""
 no docstring 
"""
```

&nbsp;

--------
# line: 45 `get_file_name`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/Utils/data_io.py#L45) online
#### function definition


```python
def get_file_name(filepath):
```
##### docstring
  


```python

"""
 no docstring 
"""
```

&nbsp;

--------
# line: 51 `load_npy_from_gz`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/Utils/data_io.py#L51) online
#### function definition


```python
def load_npy_from_gz(filepath):
```
##### docstring
  


```python

"""
 no docstring 
"""
```

&nbsp;

--------
# line: 56 `save_npy_to_gz`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/Utils/data_io.py#L56) online
#### function definition


```python
def save_npy_to_gz(filepath, data):
```
##### docstring
  


```python

"""
 no docstring 
"""
```

&nbsp;

--------
# line: 62 `save_json`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/Utils/data_io.py#L62) online
#### function definition


```python
def save_json(filepath, content, append=False):
```
##### docstring
  


```python

"""
    Saves content to a JSON file
    
    :param filepath: path to a file (must include .json)
    :param content: dictionary of stuff to save
"""
```

&nbsp;

--------
# line: 81 `save_yaml`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/Utils/data_io.py#L81) online
#### function definition


```python
def save_yaml(filepath, content, append=False, topcomment=None):
```
##### docstring
  


```python

"""
    Saves content to a yaml file
    
    :param filepath: path to a file (must include .yaml)
    :param content: dictionary of stuff to save
"""
```

&nbsp;

--------
# line: 103 `load_json`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/Utils/data_io.py#L103) online
#### function definition


```python
def load_json(filepath):
```
##### docstring
  


```python

"""
    Load a JSON file
    
    :param filepath: path to a file
"""
```

&nbsp;

--------
# line: 117 `load_yaml`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/Utils/data_io.py#L117) online
#### function definition


```python
def load_yaml(filepath):
```
##### docstring
  


```python

"""
    Load a YAML file
    
    :param filepath: path to yaml file
"""
```

&nbsp;

--------
# line: 131 `load_volume_file`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/Utils/data_io.py#L131) online
#### function definition


```python
def load_volume_file(filepath):
```
##### docstring
  


```python

"""
    Load a volume file (e.g., .nii) and returns the data
    
    :param filepath: path to file
    :param **kwargs: 
"""
```

&nbsp;

--------
# line: 149 `load_mesh_from_file`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/Utils/data_io.py#L149) online
#### function definition


```python
def load_mesh_from_file(filepath, *args, **kwargs):
```
##### docstring
  


```python

"""
    Load a a mesh or volume from files like .obj, .stl, ...
    
    :param filepath: path to file
    :param **kwargs: 
"""
```

&nbsp;

--------
# line: 180 `connected_to_internet`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/Utils/data_io.py#L180) online
#### function definition


```python
def connected_to_internet(url='http://www.google.com/', timeout=5):
```
##### docstring
  


```python

"""
    Check that there is an internet connection
    
    :param url: url to use for testing (Default value = 'http://www.google.com/')
    :param timeout:  timeout to wait for [in seconds] (Default value = 5)
"""
```

&nbsp;

--------
# line: 196 `send_query`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/Utils/data_io.py#L196) online
#### function definition


```python
def send_query(query_string, clean=False):
```
##### docstring
  


```python

"""
    Send a query/request to a website
    
    :param query_string: string with query content
    :param clean:  (Default value = False)
"""
```

&nbsp;

--------
# line: 215 `get_probe_points_from_sharptrack`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/Utils/data_io.py#L215) online
#### function definition


```python
def get_probe_points_from_sharptrack(points_filepath, scale_factor=10):
```
##### docstring
  


```python

"""
    Loads the location of the of probe points as extracted by SharpTrack
    [https://github.com/cortex-lab/allenCCF].
    
    :param points_filepath: str, path to a .mat file with probe points
    :param scale_factor: 10, sharptrack uses a 10um reference atlas so the 
            coordinates need to be scaled to match brainrender's
"""
```