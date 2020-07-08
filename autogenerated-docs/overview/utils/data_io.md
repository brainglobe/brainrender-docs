# data\_io

## Contents

* [line: 15 - `listdir`](data_io.md#line-15---listdir)
* [line: 28 - `get_subdirs`](data_io.md#line-28---get_subdirs)
* [line: 35 - `check_file_exists`](data_io.md#line-35---check_file_exists)
* [line: 45 - `get_file_name`](data_io.md#line-45---get_file_name)
* [line: 51 - `load_npy_from_gz`](data_io.md#line-51---load_npy_from_gz)
* [line: 56 - `save_npy_to_gz`](data_io.md#line-56---save_npy_to_gz)
* [line: 62 - `save_json`](data_io.md#line-62---save_json)
* [line: 81 - `save_yaml`](data_io.md#line-81---save_yaml)
* [line: 103 - `load_json`](data_io.md#line-103---load_json)
* [line: 117 - `load_yaml`](data_io.md#line-117---load_yaml)
* [line: 131 - `load_volume_file`](data_io.md#line-131---load_volume_file)
* [line: 149 - `load_mesh_from_file`](data_io.md#line-149---load_mesh_from_file)
* [line: 180 - `connected_to_internet`](data_io.md#line-180---connected_to_internet)
* [line: 196 - `send_query`](data_io.md#line-196---send_query)
* [line: 215 - `get_probe_points_from_sharptrack`](data_io.md#line-215---get_probe_points_from_sharptrack)

## line: 15 - `listdir`

```text
def listdir(fld):
```

> List the files into a folder with the coplete file path instead of the relative file path like os.listdir.  
> :param fld: string, folder path

## line: 28 - `get_subdirs`

```text
def get_subdirs(folderpath):
```

> Returns the subfolders in a given folder

## line: 35 - `check_file_exists`

```text
def check_file_exists(filepath, raise_error=False):
```

> no docstring

## line: 45 - `get_file_name`

```text
def get_file_name(filepath):
```

> no docstring

## line: 51 - `load_npy_from_gz`

```text
def load_npy_from_gz(filepath):
```

> no docstring

## line: 56 - `save_npy_to_gz`

```text
def save_npy_to_gz(filepath, data):
```

> no docstring

## line: 62 - `save_json`

```text
def save_json(filepath, content, append=False):
```

> Saves content to a JSON file  
> :param filepath: path to a file \(must include .json\)  
> :param content: dictionary of stuff to save

## line: 81 - `save_yaml`

```text
def save_yaml(filepath, content, append=False, topcomment=None):
```

> Saves content to a yaml file  
> :param filepath: path to a file \(must include .yaml\)  
> :param content: dictionary of stuff to save

## line: 103 - `load_json`

```text
def load_json(filepath):
```

> Load a JSON file  
> :param filepath: path to a file

## line: 117 - `load_yaml`

```text
def load_yaml(filepath):
```

> Load a YAML file  
> :param filepath: path to yaml file

## line: 131 - `load_volume_file`

```text
def load_volume_file(filepath):
```

> Load a volume file \(e.g., .nii\) and returns the data  
> :param filepath: path to file  
> :param \*\*kwargs:

## line: 149 - `load_mesh_from_file`

```text
def load_mesh_from_file(filepath, *args, **kwargs):
```

> Load a a mesh or volume from files like .obj, .stl, ...  
> :param filepath: path to file  
> :param \*\*kwargs:

## line: 180 - `connected_to_internet`

```text
def connected_to_internet(url='http://www.google.com/', timeout=5):
```

> Check that there is an internet connection  
> :param url: url to use for testing \(Default value = '[http://www.google.com/](http://www.google.com/)'\)  
> :param timeout: timeout to wait for \[in seconds\] \(Default value = 5\)

## line: 196 - `send_query`

```text
def send_query(query_string, clean=False):
```

> Send a query/request to a website  
> :param query\_string: string with query content  
> :param clean: \(Default value = False\)

## line: 215 - `get_probe_points_from_sharptrack`

```text
def get_probe_points_from_sharptrack(points_filepath, scale_factor=10):
```

> Loads the location of the of probe points as extracted by SharpTrack\[[https://github.com/cortex-lab/allenCCF](https://github.com/cortex-lab/allenCCF)\].  
> :param points\_filepath: str, path to a .mat file with probe points  
> :param scale\_factor: 10, sharptrack uses a 10um reference atlas so the coordinates need to be scaled to match brainrender's

