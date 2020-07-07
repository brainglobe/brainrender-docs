# colors

## Contents

* [line: 392 - `get_random_colormap`](colors.md#line-392---get_random_colormap)
* [line: 396 - `get_n_shades_of`](colors.md#line-396---get_n_shades_of)
* [line: 409 - `_isSequence`](colors.md#line-409---_issequence)
* [line: 425 - `getColor`](colors.md#line-425---getcolor)
* [line: 510 - `getColorName`](colors.md#line-510---getcolorname)
* [line: 529 - `hsv2rgb`](colors.md#line-529---hsv2rgb)
* [line: 539 - `rgb2hsv`](colors.md#line-539---rgb2hsv)
* [line: 549 - `rgb2int`](colors.md#line-549---rgb2int)
* [line: 563 - `colorMap`](colors.md#line-563---colormap)
* [line: 629 - `makePalette`](colors.md#line-629---makepalette)
* [line: 684 - `get_random_colors`](colors.md#line-684---get_random_colors)
* [line: 701 - `check_colors`](colors.md#line-701---check_colors)

## line: 392 - `get_random_colormap`

```text
def get_random_colormap():
```

> no docstring

## line: 396 - `get_n_shades_of`

```text
def get_n_shades_of(shade, n):
```

:param shade: color  
:param n: numnber of colors

## line: 409 - `_isSequence`

```text
def _isSequence(arg):
```

:param arg: item to check

## line: 425 - `getColor`

```text
def getColor(rgb=None, hsv=None):
```

> Convert a color or list of colors to \(r,g,b\) format from many different input formats.  
> :param bool: hsv: if set to `True`, rgb is assumed as \(hue, saturation, value\).Example: - RGB = \(255, 255, 255\), corresponds to white - rgb = \(1,1,1\) is white - hex = \#FFFF00 is yellow - string = 'white' - string = 'w' is white nickname - string = 'dr' is darkred - int = 7 picks color nr. 7 in a predefined color list - int = -7 picks color nr. 7 in a different predefined list\|colorcubes\| \|colorcubes.py\|\_  
> :param rgb: \(Default value = None\)  
> :param hsv: \(Default value = None\)

## line: 510 - `getColorName`

```text
def getColorName(c):
```

> Find the name of a color.\|colorpalette\| \|colorpalette.py\|\_  
> :param c: c

## line: 529 - `hsv2rgb`

```text
def hsv2rgb(hsv):
```

> Convert HSV to RGB color.  
> :param hsv: gsv

## line: 539 - `rgb2hsv`

```text
def rgb2hsv(rgb):
```

> Convert RGB to HSV color.  
> :param rgb: rgb

## line: 549 - `rgb2int`

```text
def rgb2int(rgb_tuple):
```

:param rgb\_tuple: rgb

## line: 563 - `colorMap`

```text
def colorMap(value, name='jet', vmin=None, vmax=None):
```

> Map a real value in range \[vmin, vmax\] to a \(r,g,b\) color scale.  
> :param value: scalar value to transform into a color:type value: float, list  
> :param name: color map name \(Default value = "jet"\):type name: str, matplotlib.colors.LinearSegmentedColormap  
> :param vmin: \(Default value = None\)  
> :param vmax: \(Default value = None\):returns: return: \(r,g,b\) color, or a list of \(r,g,b\) colors... note:: Most frequently used color maps: \|colormaps\| Matplotlib full list: .. image:: [https://matplotlib.org/1.2.1/\_images/show\_colormaps.png](https://matplotlib.org/1.2.1/_images/show_colormaps.png).. tip:: Can also use directly a matplotlib color map: :Example: .. code-block:: python from vedo import colorMap import matplotlib.cm as cm print\( colorMap\(0.2, cm.flag, 0, 1\) \) \(1.0, 0.809016994374948, 0.6173258487801733\)

## line: 629 - `makePalette`

```text
def makePalette(N, *colors):
```

> Generate N colors starting from `color1` to `color2`by linear interpolation HSV in or RGB spaces.Adapted from vedo makePalette function  
> :param int: N: number of output colors.  
> :param colors: input colors, any number of colors with 0 &lt; ncolors &lt;= N is okay.

## line: 684 - `get_random_colors`

```text
def get_random_colors(n_colors=1):
```

:param n\_colors: \(Default value = 1\)

## line: 701 - `check_colors`

```text
def check_colors(color):
```

:param color: color

