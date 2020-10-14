



Contents
========

* [**`get_actor_bounds`** [#10]](#get_actor_bounds-10)
* [**`get_actor_midpoint`** [#23]](#get_actor_midpoint-23)
* [**`mirror_actor_at_point`** [#33]](#mirror_actor_at_point-33)
* [**`set_line`** [#88]](#set_line-88)
* [**`edit_actor`** [#104]](#edit_actor-104)


&nbsp;

--------
# **`get_actor_bounds`** [#10]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/Utils/actors_funcs.py#L10) online

```python
def get_actor_bounds(actor):
```

&nbsp;  
docstring:

```text
Gets the AP-DV-ML bounds of an actor

```

&nbsp;

--------
# **`get_actor_midpoint`** [#23]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/Utils/actors_funcs.py#L23) online

```python
def get_actor_midpoint(actor):
```

&nbsp;  
docstring:

```text
Get's the coordinates of the midpoint of an

actor (vedo.Mesh)

```

&nbsp;

--------
# **`mirror_actor_at_point`** [#33]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/Utils/actors_funcs.py#L33) online

```python
def mirror_actor_at_point(actor, point, axis='x'):
```

&nbsp;  
docstring:

```text
Mirror an actor around a point

:param actor:

:param point:

:param axis:  (Default value = 'x')

```

&nbsp;

--------
# **`set_line`** [#88]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/Utils/actors_funcs.py#L88) online

```python
def set_line(actor, lw=None, c=None):
```

&nbsp;  
docstring:

```text
set an actor's look to specify the line width and color

:param actor:

:param lw:  (Default value = None)

:param c:  (Default value = None)

```

&nbsp;

--------
# **`edit_actor`** [#104]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/Utils/actors_funcs.py#L104) online

```python
def edit_actor(actor, wireframe=False, solid=False, color=False,
    line=False, line_kwargs={}, upsample=False, downsample=False,
    smooth=False):
```

&nbsp;  
docstring:

```text
Apply a set of functions to edit an actor's look.

:param actor:

:param wireframe: if true, change look to wireframe (Default value =
    False)

:param solid: if true change look to soi=lid (Default value = False)

:param color: specify new color (Default value = False)

:param line: if true, edit the line's look (Default value = False)

:param line_kwargs: specify width and color of line (Default value =
    {})

:param upsample: if true, increase resolution (Default value = False)

:param downsample: if true, decrease resolution (Default value =
    False)

:param smooth: if true, smoothen actor (Default value = False)

```