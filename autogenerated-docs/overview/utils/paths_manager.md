# paths\_manager

## Contents

* [**Paths**](paths_manager.md#paths)
  * [line: 69 - `__init__`](paths_manager.md#line-69---__init__)

## **Paths**

### line: 69 - `__init__`

```text
def __init__(self, base_dir=None, **kwargs):
```

> Parses a YAML file to get data folders paths. Stores paths to a number of folders used throughtout brainrender. Other classes \(e.g. brainrender.Scene\) subclass Paths.  
> :param base\_dir: str with path to directory to use to save data. If none the user's base directiry is used.  
> :param kwargs: use the name of a folder as key and a path as argument to specify the path of individual subfolders

