



Contents
========

* [**`parse_tractography_colors`** [#25]](#parse_tractography_colors-25)
* [**`experiments_source_search`** [#121]](#experiments_source_search-121)
* [**`parse_streamline`** [#179]](#parse_streamline-179)
* [**`make_url_given_id`** [#255]](#make_url_given_id-255)
* [**`download_streamlines`** [#267]](#download_streamlines-267)
* [**`extract_ids_from_csv`** [#311]](#extract_ids_from_csv-311)
* [**`parse_sharptrack`** [#362]](#parse_sharptrack-362)


&nbsp;

--------
# **`parse_tractography_colors`** [#25]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/ABA/aba_utils.py#L25) online

```python
def parse_tractography_colors(tractography, include_all_inj_regions,
    color=None, color_by='manual', VIP_regions=[], VIP_color=None,
    others_color='salmon'):
```

&nbsp;  
docstring:

```text
parses color arguments to render tracrography data

:param tractography: list of dictionaries with tractography data

:param color: color of rendered tractography data

:param color_by: str, specifies which criteria to use to color the
    tractography (Default value = "manual")

Options:

- manual: the user needs to provide a color or list of colors

- target_region: tracts are colored according to the region where the
    injection was done.

if VIP_regions is passed, then only tracts for the VIP regions are
    colored

:param VIP_regions: list of brain regions with VIP treatement (Default
    value = [])

:param VIP_color: str, color to use for VIP data (Default value =
    None)

:param include_all_inj_regions: bool (Default value = False)

:param others_color: str, color for not VIP data (Default value =
    "white")

```

&nbsp;

--------
# **`experiments_source_search`** [#121]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/ABA/aba_utils.py#L121) online

```python
def experiments_source_search(mca, SOI, *args, source=True, **kwargs):
```

&nbsp;  
docstring:

```text
Returns data about experiments whose injection was in the SOI,
    structure of interest

:param SOI: str, structure of interest. Acronym of structure to use as
    seed for teh search

:param *args:

:param source:  (Default value = True)

:param **kwargs:

```

&nbsp;

--------
# **`parse_streamline`** [#179]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/ABA/aba_utils.py#L179) online

```python
def parse_streamline(*args, filepath=None, data=None,
    show_injection_site=True, color='ivory', alpha=0.8, radius=10,
    **kwargs):
```

&nbsp;  
docstring:

```text
Given a path to a .json file with streamline data (or the data
    themselves), render the streamline as tubes actors.

Either  filepath or data should be passed

:param filepath: str, optional. Path to .json file with streamline
    data (Default value = None)

:param data: panadas.DataFrame, optional. DataFrame with streamline
    data. (Default value = None)

:param color: str color of the streamlines (Default value = 'ivory')

:param alpha: float transparency of the streamlines (Default value =
    .8)

:param radius: int radius of the streamlines actor (Default value =
    10)

:param show_injection_site: bool, if True spheres are used to render
    the injection volume (Default value = True)

:param *args:

:param **kwargs:

```

&nbsp;

--------
# **`make_url_given_id`** [#255]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/ABA/aba_utils.py#L255) online

```python
def make_url_given_id(expid):
```

&nbsp;  
docstring:

```text
Get url of JSON file for an experiment, give it's ID number

:param expid: int with experiment ID number

```

&nbsp;

--------
# **`download_streamlines`** [#267]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/ABA/aba_utils.py#L267) online

```python
def download_streamlines(eids, streamlines_folder=None):
```

&nbsp;  
docstring:

```text
Given a list of expeirmental IDs, it downloads the streamline data
    from the https://neuroinformatics.nl cache and saves them as

json files.

:param eids: list of integers with experiments IDs

:param streamlines_folder: str path to the folder where the JSON files
    should be saved, if None the default is used (Default value = None)

```

&nbsp;

--------
# **`extract_ids_from_csv`** [#311]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/ABA/aba_utils.py#L311) online

```python
def extract_ids_from_csv(csv_file, download=False, **kwargs):
```

&nbsp;  
docstring:

```text
Parse CSV file to extract experiments IDs and link to downloadable
    streamline data

Given a CSV file with info about experiments downloaded from:
    http://connectivity.brain-map.org

extract experiments ID and get links to download (compressed)
    streamline data from https://neuroinformatics.nl.

Also return the experiments IDs to download data from:
    https://neuroinformatics.nl/HBP/allen-connectivity-viewer/streamline-
    downloader.html

:param csv_file: str with path to csv file

:param download: if True the data are downloaded automatically
    (Default value = False)

:param **kwargs:

```

&nbsp;

--------
# **`parse_sharptrack`** [#362]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/ABA/aba_utils.py#L362) online

```python
def parse_sharptrack(atlas, probe_points_file, name,
    color_by_region=True, color='salmon', radius=30,
    probe_color='blackboard', probe_radius=15, probe_alpha=1):
```

&nbsp;  
docstring:

```text
Visualises the position of an implanted probe in the brain.

Uses the location of points along the probe extracted with SharpTrack

[https://github.com/cortex-lab/allenCCF].

It renders the position of points along the probe and a line fit
    through them.

Code contributed by @tbslv on github.

```