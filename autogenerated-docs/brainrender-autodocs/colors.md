# colors

## Contents

* [**`get_random_colormap`** \[\#392\]](colors.md#get_random_colormap-392)
* [**`get_n_shades_of`** \[\#396\]](colors.md#get_n_shades_of-396)
* [**`_isSequence`** \[\#409\]](colors.md#_issequence-409)
* [**`getColor`** \[\#425\]](colors.md#getcolor-425)
* [**`getColorName`** \[\#510\]](colors.md#getcolorname-510)
* [**`hsv2rgb`** \[\#529\]](colors.md#hsv2rgb-529)
* [**`rgb2hsv`** \[\#539\]](colors.md#rgb2hsv-539)
* [**`rgb2int`** \[\#549\]](colors.md#rgb2int-549)
* [**`colorMap`** \[\#563\]](colors.md#colormap-563)
* [**`makePalette`** \[\#629\]](colors.md#makepalette-629)
* [**`get_random_colors`** \[\#684\]](colors.md#get_random_colors-684)
* [**`check_colors`** \[\#701\]](colors.md#check_colors-701)

## **`get_random_colormap`** \[\#392\]

Check the [_**`source code`**_](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/colors.py#L392) online

```python
def get_random_colormap():
```

   
docstring:

no docstring

## **`get_n_shades_of`** \[\#396\]

Check the [_**`source code`**_](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/colors.py#L396) online

```python
def get_n_shades_of(shade, n):
```

   
docstring:

```text
:param shade:  color

:param n: numnber of colors
```

## **`_isSequence`** \[\#409\]

Check the [_**`source code`**_](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/colors.py#L409) online

```python
def _isSequence(arg):
```

   
docstring:

```text
:param arg:   item to check
```

## **`getColor`** \[\#425\]

Check the [_**`source code`**_](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/colors.py#L425) online

```python
def getColor(rgb=None, hsv=None):
```

   
docstring:

```text
Convert a color or list of colors to (r,g,b) format from many
    different input formats.

:param bool: hsv: if set to `True`, rgb is assumed as (hue,
    saturation, value).

Example:

 - RGB= (255, 255, 255), corresponds to white

 - rgb= (1,1,1) is white

 - hex= #FFFF00 is yellow

 - string = 'white'

 - string = 'w' is white nickname

 - string = 'dr' is darkred

 - int=  7 picks color nr. 7 in a predefined color list

 - int= -7 picks color nr. 7 in a different predefined list

|colorcubes| |colorcubes.py|_

:param rgb:  (Default value = None)

:param hsv:  (Default value = None)
```

## **`getColorName`** \[\#510\]

Check the [_**`source code`**_](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/colors.py#L510) online

```python
def getColorName(c):
```

   
docstring:

```text
Find the name of a color.

|colorpalette| |colorpalette.py|_

:param c: c
```

## **`hsv2rgb`** \[\#529\]

Check the [_**`source code`**_](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/colors.py#L529) online

```python
def hsv2rgb(hsv):
```

   
docstring:

```text
Convert HSV to RGB color.

:param hsv: gsv
```

## **`rgb2hsv`** \[\#539\]

Check the [_**`source code`**_](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/colors.py#L539) online

```python
def rgb2hsv(rgb):
```

   
docstring:

```text
Convert RGB to HSV color.

:param rgb: rgb
```

## **`rgb2int`** \[\#549\]

Check the [_**`source code`**_](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/colors.py#L549) online

```python
def rgb2int(rgb_tuple):
```

   
docstring:

```text
:param rgb_tuple: rgb
```

## **`colorMap`** \[\#563\]

Check the [_**`source code`**_](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/colors.py#L563) online

```python
def colorMap(value, name='jet', vmin=None, vmax=None):
```

   
docstring:

```text
Map a real value in range [vmin, vmax] to a (r,g,b) color scale.

:param value: scalar value to transform into a color

:type value: float, list

:param name: color map name (Default value = "jet")

:type name: str, matplotlib.colors.LinearSegmentedColormap

:param vmin:  (Default value = None)

:param vmax:  (Default value = None)

:returns: return: (r,g,b) color, or a list of (r,g,b) colors.

.. note:: Most frequently used color maps:

|colormaps|

Matplotlib full list:

.. image:: https://matplotlib.org/1.2.1/_images/show_colormaps.png

.. tip:: Can also use directly a matplotlib color map:

:Example:

.. code-block:: python

from vedo import colorMap

import matplotlib.cm as cm

print( colorMap(0.2, cm.flag, 0, 1) )

(1.0, 0.809016994374948, 0.6173258487801733)
```

## **`makePalette`** \[\#629\]

Check the [_**`source code`**_](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/colors.py#L629) online

```python
def makePalette(N, *colors):
```

   
docstring:

```text
Generate N colors starting from `color1` to `color2`

by linear interpolation HSV in or RGB spaces.

Adapted from vedo makePalette function

:param int: N: number of output colors.

:param colors: input colors, any number of colors with 0 < ncolors <=
    N is okay.
```

## **`get_random_colors`** \[\#684\]

Check the [_**`source code`**_](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/colors.py#L684) online

```python
def get_random_colors(n_colors=1):
```

   
docstring:

```text
:param n_colors:  (Default value = 1)
```

## **`check_colors`** \[\#701\]

Check the [_**`source code`**_](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/colors.py#L701) online

```python
def check_colors(color):
```

   
docstring:

```text
:param color: color
```

