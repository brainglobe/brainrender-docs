



Contents
========

* [**`listdir`** [#15]](#listdir-15)
* [**`get_subdirs`** [#26]](#get_subdirs-26)
* [**`load_cells_from_file`** [#35]](#load_cells_from_file-35)
* [**`load_npy_from_gz`** [#89]](#load_npy_from_gz-89)
* [**`save_npy_to_gz`** [#96]](#save_npy_to_gz-96)
* [**`save_yaml`** [#103]](#save_yaml-103)
* [**`load_json`** [#126]](#load_json-126)
* [**`load_yaml`** [#140]](#load_yaml-140)
* [**`load_volume_file`** [#152]](#load_volume_file-152)
* [**`load_mesh_from_file`** [#170]](#load_mesh_from_file-170)
* [**`get_probe_points_from_sharptrack`** [#192]](#get_probe_points_from_sharptrack-192)


&nbsp;

--------
# **`listdir`** [#15]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/Utils/data_io.py#L15) online

```python
def listdir(fld):
```

&nbsp;  
docstring:

```text
List the files into a folder with the complete file path instead of
    the relative file path like os.listdir.

:param fld: string, folder path

```

&nbsp;

--------
# **`get_subdirs`** [#26]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/Utils/data_io.py#L26) online

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
# **`load_cells_from_file`** [#35]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/Utils/data_io.py#L35) online

```python
def load_cells_from_file(filepath, hdf_key='hdf'):
```

&nbsp;  
docstring:

no docstring

&nbsp;

--------
# **`load_npy_from_gz`** [#89]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/Utils/data_io.py#L89) online

```python
def load_npy_from_gz(filepath):
```

&nbsp;  
docstring:

no docstring

&nbsp;

--------
# **`save_npy_to_gz`** [#96]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/Utils/data_io.py#L96) online

```python
def save_npy_to_gz(filepath, data):
```

&nbsp;  
docstring:

no docstring

&nbsp;

--------
# **`save_yaml`** [#103]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/Utils/data_io.py#L103) online

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
# **`load_json`** [#126]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/Utils/data_io.py#L126) online

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
# **`load_yaml`** [#140]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/Utils/data_io.py#L140) online

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
# **`load_volume_file`** [#152]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/Utils/data_io.py#L152) online

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
# **`load_mesh_from_file`** [#170]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/Utils/data_io.py#L170) online

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
# **`get_probe_points_from_sharptrack`** [#192]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/Utils/data_io.py#L192) online

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