



Contents
========

* [**`check_gene_cached`** [#13]](#check_gene_cached-13)
* [**`download_and_cache`** [#36]](#download_and_cache-36)
* [**`load_cached_gene`** [#56]](#load_cached_gene-56)
* [**`read_raw`** [#72]](#read_raw-72)


&nbsp;

--------
# **`check_gene_cached`** [#13]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/gene_expression/ge_utils.py#L13) online

```python
def check_gene_cached(cache_folder, gene_id, exp_id):
```

&nbsp;  
docstring:

```text
A gene is saved in a folder in cache_folder

with gene_id-exp_id as name. If the folder doesn't

exist the gene is not cached.

:param cache_folder: str, path to general cache folder for all data

:param gene_id: str name of gene

:param exp_id: id of experiment

```

&nbsp;

--------
# **`download_and_cache`** [#36]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/gene_expression/ge_utils.py#L36) online

```python
def download_and_cache(url, cachedir):
```

&nbsp;  
docstring:

```text
Given a url to download a gene's ISH experiment data,

this function download and unzips the data

:param url: str, utl to download data

:param cachedir: str, path to folder where data will be downloaded

```

&nbsp;

--------
# **`load_cached_gene`** [#56]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/gene_expression/ge_utils.py#L56) online

```python
def load_cached_gene(cache, metric, grid_size):
```

&nbsp;  
docstring:

```text
Loads a gene's data from cache

```

&nbsp;

--------
# **`read_raw`** [#72]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/gene_expression/ge_utils.py#L72) online

```python
def read_raw(filepath, grid_size):
```

&nbsp;  
docstring:

```text
reads a .raw file with gene expression data

downloaded from the Allen atlas and returns

a numpy array with the correct grid_size.

See as reference:

http://help.brain-map.org/display/mousebrain/API#API-
    Expression3DGridsz

:param filepath: str or Path object

```