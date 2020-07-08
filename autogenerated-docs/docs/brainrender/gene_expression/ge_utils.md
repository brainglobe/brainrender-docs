



Contents
========

* [line: 11 - `check_gene_cached`](#line-11---check_gene_cached)
* [line: 34 - `download_and_cache`](#line-34---download_and_cache)
* [line: 54 - `load_cached_gene`](#line-54---load_cached_gene)
* [line: 70 - `read_raw`](#line-70---read_raw)


&nbsp;

--------
# line: 11 - `check_gene_cached`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/gene_expression/ge_utils.py#L11) online
#### function definition


```python
def check_gene_cached(cache_folder, gene_id, exp_id):
```
##### docstring
  


```python

"""
    A gene is saved in a folder in cache_folder
    with gene_id-exp_id as name. If the folder doesn't
    exist the gene is not cached.
    
    :param cache_folder: str, path to general cache folder for all data
    :param gene_id: str name of gene
    :param exp_id: id of experiment 
"""
```

&nbsp;

--------
# line: 34 - `download_and_cache`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/gene_expression/ge_utils.py#L34) online
#### function definition


```python
def download_and_cache(url, cachedir):
```
##### docstring
  


```python

"""
    Given a url to download a gene's ISH experiment data, 
    this function download and unzips the data
    
    :param url: str, utl to download data
    :param cachedir: str, path to folder where data will be downloaded
"""
```

&nbsp;

--------
# line: 54 - `load_cached_gene`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/gene_expression/ge_utils.py#L54) online
#### function definition


```python
def load_cached_gene(cache, metric, grid_size):
```
##### docstring
  


```python

"""
    Loads a gene's data from cache
"""
```

&nbsp;

--------
# line: 70 - `read_raw`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/gene_expression/ge_utils.py#L70) online
#### function definition


```python
def read_raw(filepath, grid_size):
```
##### docstring
  


```python

"""
    reads a .raw file with gene expression data 
    downloaded from the Allen atlas and returns 
    a numpy array with the correct grid_size.
    See as reference:
        http://help.brain-map.org/display/mousebrain/API#API-Expression3DGridsz
    
    :param filepath: str or Path object
"""
```