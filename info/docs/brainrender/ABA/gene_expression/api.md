



Contents
========

* [**GeneExpressionAPI**](#geneexpressionapi)
	* [line: 36 - `__init__`](#line-36---__init__)
	* [line: 42 - `get_all_genes`](#line-42---get_all_genes)
	* [line: 50 - `get_gene_id_by_name`](#line-50---get_gene_id_by_name)
	* [line: 67 - `get_gene_symbol_by_id`](#line-67---get_gene_symbol_by_id)
	* [line: 82 - `get_gene_experiments`](#line-82---get_gene_experiments)
	* [line: 107 - `download_gene_data`](#line-107---download_gene_data)
	* [line: 140 - `get_gene_data`](#line-140---get_gene_data)
	* [line: 164 - `griddata_to_volume`](#line-164---griddata_to_volume)


&nbsp;

--------

--------
# **GeneExpressionAPI**




--------
## line: 36 - `__init__`
  
```  
def __init__(self, base_dir=None, **kwargs):
```


>  no docstring

--------
## line: 42 - `get_all_genes`
  
```  
def get_all_genes(self):
```
>Download metadata about all the genes available in the Allen gene expression dataset

--------
## line: 50 - `get_gene_id_by_name`
  
```  
def get_gene_id_by_name(self, gene_name):
```


>  no docstring

--------
## line: 67 - `get_gene_symbol_by_id`
  
```  
def get_gene_symbol_by_id(self, gene_id):
```


>  no docstring

--------
## line: 82 - `get_gene_experiments`
  
```  
def get_gene_experiments(self, gene_symbol):
```
>Given a gene_symbol it returns the list of ISHexperiments for this gene  
:param gene_symbol: str, self.genes.gene_symbol

--------
## line: 107 - `download_gene_data`
  
```  
def download_gene_data(self, gene):
```
>Downloads a gene's data from the Allen Institute Gene Expression dataset and saves to cache. See: http://help.brain-map.org/display/api/Downloading+3-D+Expression+Grid+Data  
:param gene: int, the gene_id for the gene being downloaded.

--------
## line: 140 - `get_gene_data`
  
```  
def get_gene_data(self, gene, exp_id, metric='energy'):
```
>Given a list of gene ids

--------
## line: 164 - `griddata_to_volume`
  
```  
def griddata_to_volume(self, griddata, min_quantile=None, min_value=None, **kwargs):
```
>Takes a 3d numpy array with volumetric gene expressionand returns a vedo.Volume.isosurface actor.The isosurface needs a lower bound threshold, this can beeither a user defined hard value (min_value) or the valuecorresponding to some percentile of the gene expression data.  
:param griddata: np.ndarray, 3d array with gene expression data  
:param min_quantile: float, percentile for threshold  
:param min_value: float, value for threshold