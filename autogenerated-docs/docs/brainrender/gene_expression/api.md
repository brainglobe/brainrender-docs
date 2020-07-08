



Contents
========

* [**GeneExpressionAPI**](#geneexpressionapi)
	* [**`__init__`** [#36]](#__init__-36)
	* [**`get_all_genes`** [#42]](#get_all_genes-42)
	* [**`get_gene_id_by_name`** [#50]](#get_gene_id_by_name-50)
	* [**`get_gene_symbol_by_id`** [#67]](#get_gene_symbol_by_id-67)
	* [**`get_gene_experiments`** [#82]](#get_gene_experiments-82)
	* [**`download_gene_data`** [#107]](#download_gene_data-107)
	* [**`get_gene_data`** [#140]](#get_gene_data-140)
	* [**`griddata_to_volume`** [#164]](#griddata_to_volume-164)


&nbsp;

--------
# **GeneExpressionAPI**




&nbsp;
## **`__init__`** [#36]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/gene_expression/api.py#L36) online

```python
def __init__(self, base_dir=None, **kwargs):
```

&nbsp;  
docstring:

no docstring

&nbsp;
## **`get_all_genes`** [#42]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/gene_expression/api.py#L42) online

```python
def get_all_genes(self):
```

&nbsp;  
docstring:

```text
Download metadata about all the genes available in the Allen gene
    expression dataset

```

&nbsp;
## **`get_gene_id_by_name`** [#50]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/gene_expression/api.py#L50) online

```python
def get_gene_id_by_name(self, gene_name):
```

&nbsp;  
docstring:

no docstring

&nbsp;
## **`get_gene_symbol_by_id`** [#67]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/gene_expression/api.py#L67) online

```python
def get_gene_symbol_by_id(self, gene_id):
```

&nbsp;  
docstring:

no docstring

&nbsp;
## **`get_gene_experiments`** [#82]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/gene_expression/api.py#L82) online

```python
def get_gene_experiments(self, gene_symbol):
```

&nbsp;  
docstring:

```text
Given a gene_symbol it returns the list of ISH

experiments for this gene

:param gene_symbol: str, self.genes.gene_symbol

```

&nbsp;
## **`download_gene_data`** [#107]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/gene_expression/api.py#L107) online

```python
def download_gene_data(self, gene):
```

&nbsp;  
docstring:

```text
Downloads a gene's data from the Allen Institute

Gene Expression dataset and saves to cache.

See: http://help.brain-
    map.org/display/api/Downloading+3-D+Expression+Grid+Data

:param gene: int, the gene_id for the gene being downloaded.

```

&nbsp;
## **`get_gene_data`** [#140]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/gene_expression/api.py#L140) online

```python
def get_gene_data(self, gene, exp_id, metric='energy'):
```

&nbsp;  
docstring:

```text
Given a list of gene ids

```

&nbsp;
## **`griddata_to_volume`** [#164]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/gene_expression/api.py#L164) online

```python
def griddata_to_volume(self, griddata, min_quantile=None,
    min_value=None, **kwargs):
```

&nbsp;  
docstring:

```text
Takes a 3d numpy array with volumetric gene expression

and returns a vedo.Volume.isosurface actor.

The isosurface needs a lower bound threshold, this can be

either a user defined hard value (min_value) or the value

corresponding to some percentile of the gene expression data.

:param griddata: np.ndarray, 3d array with gene expression data

:param min_quantile: float, percentile for threshold

:param min_value: float, value for threshold

```