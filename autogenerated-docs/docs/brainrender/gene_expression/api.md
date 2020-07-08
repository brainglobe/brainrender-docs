



Contents
========

* [**GeneExpressionAPI**](#geneexpressionapi)
* [line: 36 `__init__`](#line-36-__init__)
* [line: 42 `get_all_genes`](#line-42-get_all_genes)
* [line: 50 `get_gene_id_by_name`](#line-50-get_gene_id_by_name)
* [line: 67 `get_gene_symbol_by_id`](#line-67-get_gene_symbol_by_id)
* [line: 82 `get_gene_experiments`](#line-82-get_gene_experiments)
* [line: 107 `download_gene_data`](#line-107-download_gene_data)
* [line: 140 `get_gene_data`](#line-140-get_gene_data)
* [line: 164 `griddata_to_volume`](#line-164-griddata_to_volume)


&nbsp;

--------

--------
# **GeneExpressionAPI**




&nbsp;

--------
# line: 36 `__init__`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/gene_expression/api.py#L36) online
#### function definition


```python
def __init__(self, base_dir=None, **kwargs):
```
##### docstring
  


```python

"""
 no docstring 
"""
```

&nbsp;

--------
# line: 42 `get_all_genes`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/gene_expression/api.py#L42) online
#### function definition


```python
def get_all_genes(self):
```
##### docstring
  


```python

"""
    Download metadata about all the genes available in the Allen gene expression dataset
"""
```

&nbsp;

--------
# line: 50 `get_gene_id_by_name`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/gene_expression/api.py#L50) online
#### function definition


```python
def get_gene_id_by_name(self, gene_name):
```
##### docstring
  


```python

"""
 no docstring 
"""
```

&nbsp;

--------
# line: 67 `get_gene_symbol_by_id`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/gene_expression/api.py#L67) online
#### function definition


```python
def get_gene_symbol_by_id(self, gene_id):
```
##### docstring
  


```python

"""
 no docstring 
"""
```

&nbsp;

--------
# line: 82 `get_gene_experiments`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/gene_expression/api.py#L82) online
#### function definition


```python
def get_gene_experiments(self, gene_symbol):
```
##### docstring
  


```python

"""
    Given a gene_symbol it returns the list of ISH
    experiments for this gene
    
    :param gene_symbol: str, self.genes.gene_symbol
"""
```

&nbsp;

--------
# line: 107 `download_gene_data`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/gene_expression/api.py#L107) online
#### function definition


```python
def download_gene_data(self, gene):
```
##### docstring
  


```python

"""
    Downloads a gene's data from the Allen Institute 
    Gene Expression dataset and saves to cache. 
    See: http://help.brain-map.org/display/api/Downloading+3-D+Expression+Grid+Data
    
    :param gene: int, the gene_id for the gene being downloaded.
"""
```

&nbsp;

--------
# line: 140 `get_gene_data`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/gene_expression/api.py#L140) online
#### function definition


```python
def get_gene_data(self, gene, exp_id, metric='energy'):
```
##### docstring
  


```python

"""
    Given a list of gene ids
"""
```

&nbsp;

--------
# line: 164 `griddata_to_volume`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/gene_expression/api.py#L164) online
#### function definition


```python
def griddata_to_volume(self, griddata, min_quantile=None, min_value=None, **kwargs):
```
##### docstring
  


```python

"""
    Takes a 3d numpy array with volumetric gene expression
    and returns a vedo.Volume.isosurface actor.
    The isosurface needs a lower bound threshold, this can be
    either a user defined hard value (min_value) or the value
    corresponding to some percentile of the gene expression data.
    
    :param griddata: np.ndarray, 3d array with gene expression data
    :param min_quantile: float, percentile for threshold
    :param min_value: float, value for threshold
"""
```