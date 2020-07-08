



Contents
========

* [**`mirror_actor_at_point`** [#6]](#mirror_actor_at_point-6)
* [**`set_wireframe`** [#60]](#set_wireframe-60)
* [**`set_solid`** [#70]](#set_solid-70)
* [**`set_color`** [#80]](#set_color-80)
* [**`set_line`** [#91]](#set_line-91)
* [**`upsample_actor`** [#106]](#upsample_actor-106)
* [**`downsample_actor`** [#117]](#downsample_actor-117)
* [**`smooth_actor`** [#128]](#smooth_actor-128)
* [**`edit_actor`** [#139]](#edit_actor-139)


&nbsp;

--------
# **`mirror_actor_at_point`** [#6]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/Utils/actors_funcs.py#L6) online

```python
def mirror_actor_at_point(actor, point, axis='x'):
```  


```text
Mirror an actor around a point
:param actor:
:param point:
:param axis:  (default value = 'x')
```

&nbsp;

--------
# **`set_wireframe`** [#60]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/Utils/actors_funcs.py#L60) online

```python
def set_wireframe(actor):
```  


```text
Set an actor's look to wireframe
:param actor:
```

&nbsp;

--------
# **`set_solid`** [#70]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/Utils/actors_funcs.py#L70) online

```python
def set_solid(actor):
```  


```text
Set an actor's look to solid
:param actor:
```

&nbsp;

--------
# **`set_color`** [#80]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/Utils/actors_funcs.py#L80) online

```python
def set_color(actor, color):
```  


```text
Set an actor's look to a specific color
:param actor:
:param color:
```

&nbsp;

--------
# **`set_line`** [#91]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/Utils/actors_funcs.py#L91) online

```python
def set_line(actor, lw=None, c=None):
```  


```text
Set an actor's look to specify the line width and color
:param actor:
:param lw:  (default value = none)
:param c:  (default value = none)
```

&nbsp;

--------
# **`upsample_actor`** [#106]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/Utils/actors_funcs.py#L106) online

```python
def upsample_actor(actor, fact=1):
```  


```text
Increase resolution of actor
:param actor:
:param fact:  (default value = 1)
```

&nbsp;

--------
# **`downsample_actor`** [#117]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/Utils/actors_funcs.py#L117) online

```python
def downsample_actor(actor, fact=0.5):
```  


```text
Reduce resolution of actor
:param actor:
:param fact:  (default value = 0. 5)
```

&nbsp;

--------
# **`smooth_actor`** [#128]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/Utils/actors_funcs.py#L128) online

```python
def smooth_actor(actor, factor=15):
```  


```text
Smooth an actor's mesh
:param actor:
:param factor:  (default value = 15)
```

&nbsp;

--------
# **`edit_actor`** [#139]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/tree/brainglobeintegration/blob/master/brainrender/Utils/actors_funcs.py#L139) online

```python
def edit_actor(actor, wireframe=False, solid=False, color=False,
    line=False, line_kwargs={}, upsample=False, downsample=False,
    smooth=False):
```  


```text
Apply a set of functions to edit an actor's look.
:param actor:
:param wireframe: if true, change look to wireframe (default value =
    false)
:param solid: if true change look to soi=lid (default value = false)
:param color: specify new color (default value = false)
:param line: if true, edit the line's look (default value = false)
:param line_kwargs: specify width and color of line (default value =
    {})
:param upsample: if true, increase resolution (default value = false)
:param downsample: if true, decrease resolution (default value =
    false)
:param smooth: if true, smoothen actor (default value = false)
```