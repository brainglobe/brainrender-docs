



Contents
========

* [**`parse_neurons_colors`** [#28]](#parse_neurons_colors-28)
* [**`parse_tractography_colors`** [#147]](#parse_tractography_colors-147)
* [**`experiments_source_search`** [#243]](#experiments_source_search-243)
* [**`parse_streamline`** [#301]](#parse_streamline-301)
* [**`make_url_given_id`** [#378]](#make_url_given_id-378)
* [**`download_streamlines`** [#390]](#download_streamlines-390)
* [**`extract_ids_from_csv`** [#430]](#extract_ids_from_csv-430)


&nbsp;

--------
# **`parse_neurons_colors`** [#28]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/ABA/aba_utils.py#L28) online

```python
def parse_neurons_colors(neurons, color):
```  


```text
Prepares the color info to render neurons
:param neurons: str, list, dict.  file(s) with neurons data or list of
    rendered neurons.
:param color: default none.  can be:
- none: each neuron is given a random color
- color: rbg, hex etc.  if a single color is passed all neurons will
    have that color
- cmap: str with name of a colormap: neurons are colored based on
    their sequential order and cmap
- dict: a dictionary specifying a color for soma, dendrites and axon
    actors, will be the same for all neurons
- list: a list of length = number of neurons with either a single
    color for each neuron
or a dictionary of colors for each neuron
```

&nbsp;

--------
# **`parse_tractography_colors`** [#147]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/ABA/aba_utils.py#L147) online

```python
def parse_tractography_colors(tractography, include_all_inj_regions,
    color=None, color_by='manual', VIP_regions=[], VIP_color=None,
    others_color='salmon'):
```  


```text
Parses color arguments to render tracrography data
:param tractography: list of dictionaries with tractography data
:param color: color of rendered tractography data
:param color_by: str, specifies which criteria to use to color the
    tractography (default value = "manual")
options:
- manual: the user needs to provide a color or list of colors
- target_region: tracts are colored according to the region where the
    injection was done.
if vip_regions is passed, then only tracts for the vip regions are
    colored
:param vip_regions: list of brain regions with vip treatement (default
    value = [])
:param vip_color: str, color to use for vip data (default value =
    none)
:param include_all_inj_regions: bool (default value = false)
:param others_color: str, color for not vip data (default value =
    "white")
```

&nbsp;

--------
# **`experiments_source_search`** [#243]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/ABA/aba_utils.py#L243) online

```python
def experiments_source_search(mca, SOI, *args, source=True, **kwargs):
```  


```text
Returns data about experiments whose injection was in the soi,
    structure of interest
:param soi: str, structure of interest.  acronym of structure to use
    as seed for teh search
:param *args:
:param source:  (default value = true)
:param **kwargs:
```

&nbsp;

--------
# **`parse_streamline`** [#301]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/ABA/aba_utils.py#L301) online

```python
def parse_streamline(*args, filepath=None, data=None,
    show_injection_site=True, color='ivory', alpha=0.8, radius=10,
    **kwargs):
```  


```text
Given a path to a . Json file with streamline data (or the data
    themselves), render the streamline as tubes actors.
either  filepath or data should be passed
:param filepath: str, optional.  path to . Json file with streamline
    data (default value = none)
:param data: panadas. Dataframe, optional.  dataframe with streamline
    data.  (default value = none)
:param color: str color of the streamlines (default value = 'ivory')
:param alpha: float transparency of the streamlines (default value = .
    8)
:param radius: int radius of the streamlines actor (default value =
    10)
:param show_injection_site: bool, if true spheres are used to render
    the injection volume (default value = true)
:param *args:
:param **kwargs:
```

&nbsp;

--------
# **`make_url_given_id`** [#378]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/ABA/aba_utils.py#L378) online

```python
def make_url_given_id(expid):
```  


```text
Get url of json file for an experiment, give it's id number
:param expid: int with experiment id number
```

&nbsp;

--------
# **`download_streamlines`** [#390]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/ABA/aba_utils.py#L390) online

```python
def download_streamlines(eids, streamlines_folder=None):
```  


```text
Given a list of expeirmental ids, it downloads the streamline data
    from the https://neuroinformatics. Nl cache and saves them as
json files.
:param eids: list of integers with experiments ids
:param streamlines_folder: str path to the folder where the json files
    should be saved, if none the default is used (default value = none)
```

&nbsp;

--------
# **`extract_ids_from_csv`** [#430]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/ABA/aba_utils.py#L430) online

```python
def extract_ids_from_csv(csv_file, download=False, **kwargs):
```  


```text
Parse csv file to extract experiments ids and link to downloadable
    streamline data
given a csv file with info about experiments downloaded from:
    http://connectivity. Brain-map. Org
extract experiments id and get links to download (compressed)
    streamline data from https://neuroinformatics. Nl.
also return the experiments ids to download data from:
    https://neuroinformatics. Nl/hbp/allen-connectivity-viewer/streamline-
    downloader. Html
:param csv_file: str with path to csv file
:param download: if true the data are downloaded automatically
    (default value = false)
:param **kwargs:
```