



Contents
========

* [**Paths**](#paths)
	* [**`__init__`** [#69]](#__init__-69)


&nbsp;

--------
# **Paths**




&nbsp;
## **`__init__`** [#69]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/Utils/paths_manager.py#L69) online

```python
def __init__(self, base_dir=None, **kwargs):
```  


```text
Parses a yaml file to get data folders paths.  stores paths to a
    number of folders used throughtout brainrender.
other classes (e. G.  brainrender. Scene) subclass paths.
:param base_dir: str with path to directory to use to save data.  if
    none the user's base directiry is used.
:param kwargs: use the name of a folder as key and a path as argument
    to specify the path of individual subfolders
```