



Contents
========

* [line: 6 - `mirror_actor_at_point`](#line-6---mirror_actor_at_point)
* [line: 60 - `set_wireframe`](#line-60---set_wireframe)
* [line: 70 - `set_solid`](#line-70---set_solid)
* [line: 80 - `set_color`](#line-80---set_color)
* [line: 91 - `set_line`](#line-91---set_line)
* [line: 106 - `upsample_actor`](#line-106---upsample_actor)
* [line: 117 - `downsample_actor`](#line-117---downsample_actor)
* [line: 128 - `smooth_actor`](#line-128---smooth_actor)
* [line: 139 - `edit_actor`](#line-139---edit_actor)


&nbsp;

--------
# line: 6 - `mirror_actor_at_point`
  
```  
def mirror_actor_at_point(actor, point, axis='x'):
```
>Mirror an actor around a point  
:param actor:   
:param point:   
:param axis:  (Default value = 'x')

&nbsp;

--------
# line: 60 - `set_wireframe`
  
```  
def set_wireframe(actor):
```
>set an actor's look to wireframe  
:param actor: 

&nbsp;

--------
# line: 70 - `set_solid`
  
```  
def set_solid(actor):
```
>set an actor's look to solid  
:param actor: 

&nbsp;

--------
# line: 80 - `set_color`
  
```  
def set_color(actor, color):
```
>set an actor's look to a specific color  
:param actor:   
:param color: 

&nbsp;

--------
# line: 91 - `set_line`
  
```  
def set_line(actor, lw=None, c=None):
```
>set an actor's look to specify the line width and color  
:param actor:   
:param lw:  (Default value = None)  
:param c:  (Default value = None)

&nbsp;

--------
# line: 106 - `upsample_actor`
  
```  
def upsample_actor(actor, fact=1):
```
>Increase resolution of actor  
:param actor:   
:param fact:  (Default value = 1)

&nbsp;

--------
# line: 117 - `downsample_actor`
  
```  
def downsample_actor(actor, fact=0.5):
```
>Reduce resolution of actor  
:param actor:   
:param fact:  (Default value = 0.5)

&nbsp;

--------
# line: 128 - `smooth_actor`
  
```  
def smooth_actor(actor, factor=15):
```
>Smooth an actor's mesh  
:param actor:   
:param factor:  (Default value = 15)

&nbsp;

--------
# line: 139 - `edit_actor`
  
```  
def edit_actor(actor, wireframe=False, solid=False, color=False, line=False, line_kwargs={}, upsample=False, downsample=False, smooth=False):
```
>Apply a set of functions to edit an actor's look.   
:param actor:   
:param wireframe: if true, change look to wireframe (Default value = False)  
:param solid: if true change look to soi=lid (Default value = False)  
:param color: specify new color (Default value = False)  
:param line: if true, edit the line's look (Default value = False)  
:param line_kwargs: specify width and color of line (Default value = {})  
:param upsample: if true, increase resolution (Default value = False)  
:param downsample: if true, decrease resolution (Default value = False)  
:param smooth: if true, smoothen actor (Default value = False)