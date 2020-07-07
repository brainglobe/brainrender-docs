# ge\_utils

## Contents

* [line: 11 - `check_gene_cached`](ge_utils.md#line-11---check_gene_cached)
* [line: 34 - `download_and_cache`](ge_utils.md#line-34---download_and_cache)
* [line: 54 - `load_cached_gene`](ge_utils.md#line-54---load_cached_gene)
* [line: 70 - `read_raw`](ge_utils.md#line-70---read_raw)

## line: 11 - `check_gene_cached`

```text
def check_gene_cached(cache_folder, gene_id, exp_id):
```

> A gene is saved in a folder in cache\_folderwith gene\_id-exp\_id as name. If the folder doesn'texist the gene is not cached.  
> :param cache\_folder: str, path to general cache folder for all data  
> :param gene\_id: str name of gene  
> :param exp\_id: id of experiment

## line: 34 - `download_and_cache`

```text
def download_and_cache(url, cachedir):
```

> Given a url to download a gene's ISH experiment data, this function download and unzips the data  
> :param url: str, utl to download data  
> :param cachedir: str, path to folder where data will be downloaded

## line: 54 - `load_cached_gene`

```text
def load_cached_gene(cache, metric, grid_size):
```

> Loads a gene's data from cache

## line: 70 - `read_raw`

```text
def read_raw(filepath, grid_size):
```

> reads a .raw file with gene expression data downloaded from the Allen atlas and returns a numpy array with the correct grid\_size.See as reference: [http://help.brain-map.org/display/mousebrain/API\#API-Expression3DGridsz](http://help.brain-map.org/display/mousebrain/API#API-Expression3DGridsz)  
> :param filepath: str or Path object

