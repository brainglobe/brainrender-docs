



Contents
========

* [**`listdir`** [#16]](#listdir-16)
* [**`get_subdirs`** [#26]](#get_subdirs-26)
* [**`load_cells_from_file`** [#34]](#load_cells_from_file-34)
* [**`load_npy_from_gz`** [#87]](#load_npy_from_gz-87)
* [**`save_npy_to_gz`** [#93]](#save_npy_to_gz-93)
* [**`save_yaml`** [#99]](#save_yaml-99)
* [**`load_json`** [#121]](#load_json-121)
* [**`load_yaml`** [#134]](#load_yaml-134)
* [**`load_volume_file`** [#145]](#load_volume_file-145)
* [**`load_mesh_from_file`** [#162]](#load_mesh_from_file-162)
* [**`get_probe_points_from_sharptrack`** [#184]](#get_probe_points_from_sharptrack-184)


&nbsp;

--------
# **`listdir`** [#16]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/Utils/data_io.py#L16) online

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
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/Utils/data_io.py#L26) online

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
# **`load_cells_from_file`** [#34]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/Utils/data_io.py#L34) online

```python
def load_cells_from_file(filepath, hdf_key='hdf'):
```

&nbsp;  
docstring:

no docstring

&nbsp;

--------
# **`load_npy_from_gz`** [#87]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/Utils/data_io.py#L87) online

```python
def load_npy_from_gz(filepath):
```

&nbsp;  
docstring:

no docstring

&nbsp;

--------
# **`save_npy_to_gz`** [#93]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/Utils/data_io.py#L93) online

```python
def save_npy_to_gz(filepath, data):
```

&nbsp;  
docstring:

no docstring

&nbsp;

--------
# **`save_yaml`** [#99]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/Utils/data_io.py#L99) online

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
# **`load_json`** [#121]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/Utils/data_io.py#L121) online

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
# **`load_yaml`** [#134]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/Utils/data_io.py#L134) online

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
# **`load_volume_file`** [#145]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/Utils/data_io.py#L145) online

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
# **`load_mesh_from_file`** [#162]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/Utils/data_io.py#L162) online

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
# **`get_probe_points_from_sharptrack`** [#184]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/Utils/data_io.py#L184) online

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