



Contents
========

* [**`check_gene_cached`**  [#11]](#check_gene_cached--11)
* [**`download_and_cache`**  [#34]](#download_and_cache--34)
* [**`load_cached_gene`**  [#54]](#load_cached_gene--54)
* [**`read_raw`**  [#70]](#read_raw--70)


&nbsp;

--------
# **`check_gene_cached`**  [#11]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/gene_expression/ge_utils.py#L11) online

```python
def check_gene_cached(cache_folder, gene_id, exp_id):
```  


```text
A gene is saved in a folder in cache_folder
with gene_id-exp_id as name.  if the folder doesn't
exist the gene is not cached. 
:param cache_folder: str, path to general cache folder for all data
:param gene_id: str name of gene
:param exp_id: id of experiment 

```

&nbsp;

--------
# **`download_and_cache`**  [#34]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/gene_expression/ge_utils.py#L34) online

```python
def download_and_cache(url, cachedir):
```  


```text
Given a url to download a gene's ish experiment data, 
this function download and unzips the data
:param url: str, utl to download data
:param cachedir: str, path to folder where data will be downloaded

```

&nbsp;

--------
# **`load_cached_gene`**  [#54]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/gene_expression/ge_utils.py#L54) online

```python
def load_cached_gene(cache, metric, grid_size):
```  


```text
Loads a gene's data from cache

```

&nbsp;

--------
# **`read_raw`**  [#70]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/gene_expression/ge_utils.py#L70) online

```python
def read_raw(filepath, grid_size):
```  


```text
Reads a . Raw file with gene expression data 
downloaded from the allen atlas and returns 
a numpy array with the correct grid_size. 
see as reference:
http://help. Brain-map. Org/display/mousebrain/api#api-expression3dgridsz
:param filepath: str or path object

```