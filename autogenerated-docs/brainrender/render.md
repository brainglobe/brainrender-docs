



Contents
========

* [**Render**](#render)
	* [**`__init__`** [#36]](#__init__-36)
	* [**`_make_custom_axes`** [#111]](#_make_custom_axes-111)
	* [**`_correct_axes`** [#148]](#_correct_axes-148)
	* [**`apply_render_style`** [#182]](#apply_render_style-182)
	* [**`render`** [#196]](#render-196)
	* [**`close`** [#260]](#close-260)
	* [**`export_for_web`** [#263]](#export_for_web-263)
	* [**`keypress`** [#300]](#keypress-300)
	* [**`take_screenshot`** [#310]](#take_screenshot-310)


&nbsp;

--------
# **Render**




&nbsp;
## **`__init__`** [#36]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/render.py#L36) online

```python
def __init__(self, verbose, display_inset, camera, screenshot_kwargs,
    use_default_key_bindings):
```

&nbsp;  
docstring:

```text
Creates and manages a Plotter instance

:param add_root: if False a rendered outline of the whole brain is
    added to the scene (default value None)

:param verbose: if False less feedback is printed to screen (default
    value True)

:param display_inset: if False the inset displaying the brain's
    outline is not rendered (but the root is added to the scene) (default
    value None)

:param camera: name of the camera parameters setting to use (controls
    the orientation of the rendered scene)

:param screenshot_kwargs: pass a dictionary with keys:

- 'folder' -> str, path to folder where to save screenshots

- 'name' -> str, filename to prepend to screenshots files

:param use_default_key_bindings: if True the defualt keybindings from
    vedo are used, otherwise

a custom function that can be used to take screenshots with the
    parameter above.

```

&nbsp;
## **`_make_custom_axes`** [#111]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/render.py#L111) online

```python
def _make_custom_axes(self):
```

&nbsp;  
docstring:

```text
When using `ruler` axes (vedy style 7), we need to

customize them a little bit, this function takes care of it.

```

&nbsp;
## **`_correct_axes`** [#148]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/render.py#L148) online

```python
def _correct_axes(self):
```

&nbsp;  
docstring:

```text
When the scene is first rendered, a transform matrix

is applied to each actor's points to correct orientation

mismatches: https://github.com/brainglobe/bg-atlasapi/issues/73

```

&nbsp;
## **`apply_render_style`** [#182]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/render.py#L182) online

```python
def apply_render_style(self):
```

&nbsp;  
docstring:

no docstring

&nbsp;
## **`render`** [#196]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/render.py#L196) online

```python
def render(self, interactive=True, video=False, camera=None,
    zoom=None, **kwargs):
```

&nbsp;  
docstring:

```text
Takes care of rendering the scene

```

&nbsp;
## **`close`** [#260]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/render.py#L260) online

```python
def close(self):
```

&nbsp;  
docstring:

no docstring

&nbsp;
## **`export_for_web`** [#263]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/render.py#L263) online

```python
def export_for_web(self, filepath='brexport.html'):
```

&nbsp;  
docstring:

```text
This function is used to export a brainrender scene

for hosting it online. It saves an html file that can

be opened in a web browser to show an interactive brainrender scene

```

&nbsp;
## **`keypress`** [#300]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/render.py#L300) online

```python
def keypress(self, key):
```

&nbsp;  
docstring:

no docstring

&nbsp;
## **`take_screenshot`** [#310]
  
Check the [***``source code``***](https://github.com/brainglobe/brainrender/blob/master/brainrender/render.py#L310) online

```python
def take_screenshot(self):
```

&nbsp;  
docstring:

no docstring