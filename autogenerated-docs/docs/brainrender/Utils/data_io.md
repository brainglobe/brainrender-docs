



Contents
========

* [**`listdir`** [#17]](#listdir-17)
* [**`get_subdirs`** [#30]](#get_subdirs-30)
* [**`check_file_exists`** [#37]](#check_file_exists-37)
* [**`get_file_name`** [#47]](#get_file_name-47)
* [**`load_cells_from_file`** [#53]](#load_cells_from_file-53)
* [**`load_npy_from_gz`** [#105]](#load_npy_from_gz-105)
* [**`save_npy_to_gz`** [#110]](#save_npy_to_gz-110)
* [**`save_json`** [#116]](#save_json-116)
* [**`save_yaml`** [#135]](#save_yaml-135)
* [**`load_json`** [#157]](#load_json-157)
* [**`load_yaml`** [#171]](#load_yaml-171)
* [**`load_volume_file`** [#185]](#load_volume_file-185)
* [**`load_mesh_from_file`** [#203]](#load_mesh_from_file-203)
* [**`connected_to_internet`** [#234]](#connected_to_internet-234)
* [**`send_query`** [#250]](#send_query-250)
* [**`get_probe_points_from_sharptrack`** [#269]](#get_probe_points_from_sharptrack-269)


&nbsp;

--------
# **`listdir`** [#17]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/Utils/data_io.py#L17) online

```python
def listdir(fld):
```

&nbsp;  
docstring:

```text
List the files into a folder with the coplete file path instead of the
    relative file path like os.listdir.

:param fld: string, folder path

```

&nbsp;

--------
# **`get_subdirs`** [#30]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/Utils/data_io.py#L30) online

```python
def get_subdirs(folderpath):
```

&nbsp;  
docstring:

```text
Returns the subfolders in a given folder

```

&nbsp;

--------
# **`check_file_exists`** [#37]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/Utils/data_io.py#L37) online

```python
def check_file_exists(filepath, raise_error=False):
```

&nbsp;  
docstring:

no docstring

&nbsp;

--------
# **`get_file_name`** [#47]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/Utils/data_io.py#L47) online

```python
def get_file_name(filepath):
```

&nbsp;  
docstring:

no docstring

&nbsp;

--------
# **`load_cells_from_file`** [#53]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/Utils/data_io.py#L53) online

```python
def load_cells_from_file(filepath, hdf_key='hdf'):
```

&nbsp;  
docstring:

no docstring

&nbsp;

--------
# **`load_npy_from_gz`** [#105]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/Utils/data_io.py#L105) online

```python
def load_npy_from_gz(filepath):
```

&nbsp;  
docstring:

no docstring

&nbsp;

--------
# **`save_npy_to_gz`** [#110]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/Utils/data_io.py#L110) online

```python
def save_npy_to_gz(filepath, data):
```

&nbsp;  
docstring:

no docstring

&nbsp;

--------
# **`save_json`** [#116]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/Utils/data_io.py#L116) online

```python
def save_json(filepath, content, append=False):
```

&nbsp;  
docstring:

```text
Saves content to a JSON file

:param filepath: path to a file (must include .json)

:param content: dictionary of stuff to save

```

&nbsp;

--------
# **`save_yaml`** [#135]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/Utils/data_io.py#L135) online

```python
def save_yaml(filepath, content, append=False, topcomment=None):
```

&nbsp;  
docstring:

```text
Saves content to a yaml file

:param filepath: path to a file (must include .yaml)

:param content: dictionary of stuff to save

```

&nbsp;

--------
# **`load_json`** [#157]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/Utils/data_io.py#L157) online

```python
def load_json(filepath):
```

&nbsp;  
docstring:

```text
Load a JSON file

:param filepath: path to a file

```

&nbsp;

--------
# **`load_yaml`** [#171]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/Utils/data_io.py#L171) online

```python
def load_yaml(filepath):
```

&nbsp;  
docstring:

```text
Load a YAML file

:param filepath: path to yaml file

```

&nbsp;

--------
# **`load_volume_file`** [#185]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/Utils/data_io.py#L185) online

```python
def load_volume_file(filepath):
```

&nbsp;  
docstring:

```text
Load a volume file (e.g., .nii) and returns the data

:param filepath: path to file

:param **kwargs:

```

&nbsp;

--------
# **`load_mesh_from_file`** [#203]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/Utils/data_io.py#L203) online

```python
def load_mesh_from_file(filepath, *args, **kwargs):
```

&nbsp;  
docstring:

```text
Load a a mesh or volume from files like .obj, .stl, ...

:param filepath: path to file

:param **kwargs:

```

&nbsp;

--------
# **`connected_to_internet`** [#234]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/Utils/data_io.py#L234) online

```python
def connected_to_internet(url='http://www.google.com/', timeout=5):
```

&nbsp;  
docstring:

```text
Check that there is an internet connection

:param url: url to use for testing (Default value =
    'http://www.google.com/')

:param timeout:  timeout to wait for [in seconds] (Default value = 5)

```

&nbsp;

--------
# **`send_query`** [#250]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/Utils/data_io.py#L250) online

```python
def send_query(query_string, clean=False):
```

&nbsp;  
docstring:

```text
Send a query/request to a website

:param query_string: string with query content

:param clean:  (Default value = False)

```

&nbsp;

--------
# **`get_probe_points_from_sharptrack`** [#269]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/Utils/data_io.py#L269) online

```python
def get_probe_points_from_sharptrack(points_filepath,
    scale_factor=10):
```

&nbsp;  
docstring:

```text
Loads the location of the of probe points as extracted by SharpTrack

[https://github.com/cortex-lab/allenCCF].

:param points_filepath: str, path to a .mat file with probe points

:param scale_factor: 10, sharptrack uses a 10um reference atlas so the

coordinates need to be scaled to match brainrender's

```