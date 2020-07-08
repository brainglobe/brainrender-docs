



Contents
========

* [line: 392 - `get_random_colormap`](#line-392---get_random_colormap)
* [line: 396 - `get_n_shades_of`](#line-396---get_n_shades_of)
* [line: 409 - `_isSequence`](#line-409---_issequence)
* [line: 425 - `getColor`](#line-425---getcolor)
* [line: 510 - `getColorName`](#line-510---getcolorname)
* [line: 529 - `hsv2rgb`](#line-529---hsv2rgb)
* [line: 539 - `rgb2hsv`](#line-539---rgb2hsv)
* [line: 549 - `rgb2int`](#line-549---rgb2int)
* [line: 563 - `colorMap`](#line-563---colormap)
* [line: 629 - `makePalette`](#line-629---makepalette)
* [line: 684 - `get_random_colors`](#line-684---get_random_colors)
* [line: 701 - `check_colors`](#line-701---check_colors)


&nbsp;

--------
# line: 392 - `get_random_colormap`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/colors.py#L392) online
#### function definition


```python
def get_random_colormap():
```
##### docstring
  


```python

"""
 no docstring 
"""
```

&nbsp;

--------
# line: 396 - `get_n_shades_of`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/colors.py#L396) online
#### function definition


```python
def get_n_shades_of(shade, n):
```
##### docstring
  


```python

"""
    :param shade:  color
    :param n: numnber of colors
"""
```

&nbsp;

--------
# line: 409 - `_isSequence`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/colors.py#L409) online
#### function definition


```python
def _isSequence(arg):
```
##### docstring
  


```python

"""
    :param arg:   item to check
"""
```

&nbsp;

--------
# line: 425 - `getColor`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/colors.py#L425) online
#### function definition


```python
def getColor(rgb=None, hsv=None):
```
##### docstring
  


```python

"""
    Convert a color or list of colors to (r,g,b) format from many different input formats.
    
    :param bool: hsv: if set to `True`, rgb is assumed as (hue, saturation, value).
    Example:
         - RGB    = (255, 255, 255), corresponds to white
         - rgb    = (1,1,1) is white
         - hex    = #FFFF00 is yellow
         - string = 'white'
         - string = 'w' is white nickname
         - string = 'dr' is darkred
         - int    =  7 picks color nr. 7 in a predefined color list
         - int    = -7 picks color nr. 7 in a different predefined list
    |colorcubes| |colorcubes.py|_
    :param rgb:  (Default value = None)
    :param hsv:  (Default value = None)
"""
```

&nbsp;

--------
# line: 510 - `getColorName`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/colors.py#L510) online
#### function definition


```python
def getColorName(c):
```
##### docstring
  


```python

"""
    Find the name of a color.
    |colorpalette| |colorpalette.py|_
    
    :param c: c 
"""
```

&nbsp;

--------
# line: 529 - `hsv2rgb`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/colors.py#L529) online
#### function definition


```python
def hsv2rgb(hsv):
```
##### docstring
  


```python

"""
    Convert HSV to RGB color.
    
    :param hsv: gsv 
"""
```

&nbsp;

--------
# line: 539 - `rgb2hsv`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/colors.py#L539) online
#### function definition


```python
def rgb2hsv(rgb):
```
##### docstring
  


```python

"""
    Convert RGB to HSV color.
    
    :param rgb: rgb 
"""
```

&nbsp;

--------
# line: 549 - `rgb2int`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/colors.py#L549) online
#### function definition


```python
def rgb2int(rgb_tuple):
```
##### docstring
  


```python

"""
    :param rgb_tuple: rgb 
"""
```

&nbsp;

--------
# line: 563 - `colorMap`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/colors.py#L563) online
#### function definition


```python
def colorMap(value, name='jet', vmin=None, vmax=None):
```
##### docstring
  


```python

"""
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
"""
```

&nbsp;

--------
# line: 629 - `makePalette`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/colors.py#L629) online
#### function definition


```python
def makePalette(N, *colors):
```
##### docstring
  


```python

"""
    Generate N colors starting from `color1` to `color2`
    by linear interpolation HSV in or RGB spaces.
    Adapted from vedo makePalette function
    
    :param int: N: number of output colors.
    :param colors: input colors, any number of colors with 0 < ncolors <= N is okay.
"""
```

&nbsp;

--------
# line: 684 - `get_random_colors`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/colors.py#L684) online
#### function definition


```python
def get_random_colors(n_colors=1):
```
##### docstring
  


```python

"""
    :param n_colors:  (Default value = 1)
"""
```

&nbsp;

--------
# line: 701 - `check_colors`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/colors.py#L701) online
#### function definition


```python
def check_colors(color):
```
##### docstring
  


```python

"""
    :param color: color 
"""
```