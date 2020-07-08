



Contents
========

* [**`get_random_colormap`** [#392]](#get_random_colormap-392)
* [**`get_n_shades_of`** [#396]](#get_n_shades_of-396)
* [**`_isSequence`** [#409]](#_issequence-409)
* [**`getColor`** [#425]](#getcolor-425)
* [**`getColorName`** [#510]](#getcolorname-510)
* [**`hsv2rgb`** [#529]](#hsv2rgb-529)
* [**`rgb2hsv`** [#539]](#rgb2hsv-539)
* [**`rgb2int`** [#549]](#rgb2int-549)
* [**`colorMap`** [#563]](#colormap-563)
* [**`makePalette`** [#629]](#makepalette-629)
* [**`get_random_colors`** [#684]](#get_random_colors-684)
* [**`check_colors`** [#701]](#check_colors-701)


&nbsp;

--------
# **`get_random_colormap`** [#392]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/colors.py#L392) online

```python
def get_random_colormap():
```  


no docstring

&nbsp;

--------
# **`get_n_shades_of`** [#396]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/colors.py#L396) online

```python
def get_n_shades_of(shade, n):
```  


```text
:param shade:  color

:param n: numnber of colors

```

&nbsp;

--------
# **`_isSequence`** [#409]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/colors.py#L409) online

```python
def _isSequence(arg):
```  


```text
:param arg:   item to check

```

&nbsp;

--------
# **`getColor`** [#425]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/colors.py#L425) online

```python
def getColor(rgb=None, hsv=None):
```  


```text
Convert a color or list of colors to (r,g,b) format from many
    different input formats.

:param bool: hsv: if set to `true`, rgb is assumed as (hue,
    saturation, value).

example:

 - rgb= (255, 255, 255), corresponds to white

 - rgb= (1,1,1) is white

 - hex= #ffff00 is yellow

 - string = 'white'

 - string = 'w' is white nickname

 - string = 'dr' is darkred

 - int=  7 picks color nr.  7 in a predefined color list

 - int= -7 picks color nr.  7 in a different predefined list

|colorcubes| |colorcubes. Py|_

:param rgb:  (default value = none)

:param hsv:  (default value = none)

```

&nbsp;

--------
# **`getColorName`** [#510]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/colors.py#L510) online

```python
def getColorName(c):
```  


```text
Find the name of a color.

|colorpalette| |colorpalette. Py|_

:param c: c

```

&nbsp;

--------
# **`hsv2rgb`** [#529]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/colors.py#L529) online

```python
def hsv2rgb(hsv):
```  


```text
Convert hsv to rgb color.

:param hsv: gsv

```

&nbsp;

--------
# **`rgb2hsv`** [#539]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/colors.py#L539) online

```python
def rgb2hsv(rgb):
```  


```text
Convert rgb to hsv color.

:param rgb: rgb

```

&nbsp;

--------
# **`rgb2int`** [#549]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/colors.py#L549) online

```python
def rgb2int(rgb_tuple):
```  


```text
:param rgb_tuple: rgb

```

&nbsp;

--------
# **`colorMap`** [#563]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/colors.py#L563) online

```python
def colorMap(value, name='jet', vmin=None, vmax=None):
```  


```text
Map a real value in range [vmin, vmax] to a (r,g,b) color scale.

:param value: scalar value to transform into a color

:type value: float, list

:param name: color map name (default value = "jet")

:type name: str, matplotlib. Colors. Linearsegmentedcolormap

:param vmin:  (default value = none)

:param vmax:  (default value = none)

:returns: return: (r,g,b) color, or a list of (r,g,b) colors.

. .  note:: most frequently used color maps:

|colormaps|

matplotlib full list:

. .  image:: https://matplotlib. Org/1. 2. 1/_images/show_colormaps.
    Png

. .  tip:: can also use directly a matplotlib color map:

:example:

. .  code-block:: python

from vedo import colormap

import matplotlib. Cm as cm

print( colormap(0. 2, cm. Flag, 0, 1) )

(1. 0, 0. 809016994374948, 0. 6173258487801733)

```

&nbsp;

--------
# **`makePalette`** [#629]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/colors.py#L629) online

```python
def makePalette(N, *colors):
```  


```text
Generate n colors starting from `color1` to `color2`

by linear interpolation hsv in or rgb spaces.

adapted from vedo makepalette function

:param int: n: number of output colors.

:param colors: input colors, any number of colors with 0 < ncolors <=
    n is okay.

```

&nbsp;

--------
# **`get_random_colors`** [#684]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/colors.py#L684) online

```python
def get_random_colors(n_colors=1):
```  


```text
:param n_colors:  (default value = 1)

```

&nbsp;

--------
# **`check_colors`** [#701]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/colors.py#L701) online

```python
def check_colors(color):
```  


```text
:param color: color

```