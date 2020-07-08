# api

## Contents

* [**GeneExpressionAPI**](api.md#geneexpressionapi)
  * [line: 36 - `__init__`](api.md#line-36---__init__)
  * [line: 42 - `get_all_genes`](api.md#line-42---get_all_genes)
  * [line: 50 - `get_gene_id_by_name`](api.md#line-50---get_gene_id_by_name)
  * [line: 67 - `get_gene_symbol_by_id`](api.md#line-67---get_gene_symbol_by_id)
  * [line: 82 - `get_gene_experiments`](api.md#line-82---get_gene_experiments)
  * [line: 107 - `download_gene_data`](api.md#line-107---download_gene_data)
  * [line: 140 - `get_gene_data`](api.md#line-140---get_gene_data)
  * [line: 164 - `griddata_to_volume`](api.md#line-164---griddata_to_volume)

## **GeneExpressionAPI**

### line: 36 - `__init__`

```text
def __init__(self, base_dir=None, **kwargs):
```

> no docstring

### line: 42 - `get_all_genes`

```text
def get_all_genes(self):
```

> Download metadata about all the genes available in the Allen gene expression dataset

### line: 50 - `get_gene_id_by_name`

```text
def get_gene_id_by_name(self, gene_name):
```

> no docstring

### line: 67 - `get_gene_symbol_by_id`

```text
def get_gene_symbol_by_id(self, gene_id):
```

> no docstring

### line: 82 - `get_gene_experiments`

```text
def get_gene_experiments(self, gene_symbol):
```

> Given a gene\_symbol it returns the list of ISHexperiments for this gene  
> :param gene\_symbol: str, self.genes.gene\_symbol

### line: 107 - `download_gene_data`

```text
def download_gene_data(self, gene):
```

> Downloads a gene's data from the Allen Institute Gene Expression dataset and saves to cache. See: [http://help.brain-map.org/display/api/Downloading+3-D+Expression+Grid+Data](http://help.brain-map.org/display/api/Downloading+3-D+Expression+Grid+Data)  
> :param gene: int, the gene\_id for the gene being downloaded.

### line: 140 - `get_gene_data`

```text
def get_gene_data(self, gene, exp_id, metric='energy'):
```

> Given a list of gene ids

### line: 164 - `griddata_to_volume`

```text
def griddata_to_volume(self, griddata, min_quantile=None, min_value=None, **kwargs):
```

> Takes a 3d numpy array with volumetric gene expressionand returns a vedo.Volume.isosurface actor.The isosurface needs a lower bound threshold, this can beeither a user defined hard value \(min\_value\) or the valuecorresponding to some percentile of the gene expression data.  
> :param griddata: np.ndarray, 3d array with gene expression data  
> :param min\_quantile: float, percentile for threshold  
> :param min\_value: float, value for threshold

