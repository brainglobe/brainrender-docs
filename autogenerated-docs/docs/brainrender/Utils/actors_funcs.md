



Contents
========

* [line: 6 `mirror_actor_at_point`](#line-6-mirror_actor_at_point)
* [line: 60 `set_wireframe`](#line-60-set_wireframe)
* [line: 70 `set_solid`](#line-70-set_solid)
* [line: 80 `set_color`](#line-80-set_color)
* [line: 91 `set_line`](#line-91-set_line)
* [line: 106 `upsample_actor`](#line-106-upsample_actor)
* [line: 117 `downsample_actor`](#line-117-downsample_actor)
* [line: 128 `smooth_actor`](#line-128-smooth_actor)
* [line: 139 `edit_actor`](#line-139-edit_actor)


&nbsp;

--------
# line: 6 `mirror_actor_at_point`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/Utils/actors_funcs.py#L6) online
#### function definition


```python
def mirror_actor_at_point(actor, point, axis='x'):
```
##### docstring
  


```python

"""
    Mirror an actor around a point
    
    :param actor: 
    :param point: 
    :param axis:  (Default value = 'x')
"""
```

&nbsp;

--------
# line: 60 `set_wireframe`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/Utils/actors_funcs.py#L60) online
#### function definition


```python
def set_wireframe(actor):
```
##### docstring
  


```python

"""
    set an actor's look to wireframe
    
    :param actor: 
"""
```

&nbsp;

--------
# line: 70 `set_solid`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/Utils/actors_funcs.py#L70) online
#### function definition


```python
def set_solid(actor):
```
##### docstring
  


```python

"""
    set an actor's look to solid
    
    :param actor: 
"""
```

&nbsp;

--------
# line: 80 `set_color`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/Utils/actors_funcs.py#L80) online
#### function definition


```python
def set_color(actor, color):
```
##### docstring
  


```python

"""
    set an actor's look to a specific color
    
    :param actor: 
    :param color: 
"""
```

&nbsp;

--------
# line: 91 `set_line`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/Utils/actors_funcs.py#L91) online
#### function definition


```python
def set_line(actor, lw=None, c=None):
```
##### docstring
  


```python

"""
    set an actor's look to specify the line width and color
    
    :param actor: 
    :param lw:  (Default value = None)
    :param c:  (Default value = None)
"""
```

&nbsp;

--------
# line: 106 `upsample_actor`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/Utils/actors_funcs.py#L106) online
#### function definition


```python
def upsample_actor(actor, fact=1):
```
##### docstring
  


```python

"""
    Increase resolution of actor
    
    :param actor: 
    :param fact:  (Default value = 1)
"""
```

&nbsp;

--------
# line: 117 `downsample_actor`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/Utils/actors_funcs.py#L117) online
#### function definition


```python
def downsample_actor(actor, fact=0.5):
```
##### docstring
  


```python

"""
    Reduce resolution of actor
    
    :param actor: 
    :param fact:  (Default value = 0.5)
"""
```

&nbsp;

--------
# line: 128 `smooth_actor`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/Utils/actors_funcs.py#L128) online
#### function definition


```python
def smooth_actor(actor, factor=15):
```
##### docstring
  


```python

"""
    Smooth an actor's mesh
    
    :param actor: 
    :param factor:  (Default value = 15)
"""
```

&nbsp;

--------
# line: 139 `edit_actor`
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/Utils/actors_funcs.py#L139) online
#### function definition


```python
def edit_actor(actor, wireframe=False, solid=False, color=False, line=False, line_kwargs={}, upsample=False, downsample=False, smooth=False):
```
##### docstring
  


```python

"""
    Apply a set of functions to edit an actor's look. 
    
    :param actor: 
    :param wireframe: if true, change look to wireframe (Default value = False)
    :param solid: if true change look to soi=lid (Default value = False)
    :param color: specify new color (Default value = False)
    :param line: if true, edit the line's look (Default value = False)
    :param line_kwargs: specify width and color of line (Default value = {})
    :param upsample: if true, increase resolution (Default value = False)
    :param downsample: if true, decrease resolution (Default value = False)
    :param smooth: if true, smoothen actor (Default value = False)
"""
```