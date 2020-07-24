



Contents
========

* [**Paths**](#paths)
	* [**`__init__`** [#69]](#__init__-69)


&nbsp;

--------
# **Paths**




&nbsp;
## **`__init__`** [#69]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/Utils/paths_manager.py#L69) online

```python
def __init__(self, base_dir=None, **kwargs):
```

&nbsp;  
docstring:

```text
Parses a YAML file to get data folders paths. Stores paths to a number
    of folders used throughtout brainrender.

Other classes (e.g. brainrender.Scene) subclass Paths.

:param base_dir: str with path to directory to use to save data. If
    none the user's base directiry is used.

:param kwargs: use the name of a folder as key and a path as argument
    to specify the path of individual subfolders

```