



Contents
========

* [**Render**](#render)
	* [**`__init__`** [#26]](#__init__-26)
	* [**`apply_render_style`** [#97]](#apply_render_style-97)
	* [**`render`** [#111]](#render-111)
	* [**`close`** [#166]](#close-166)
	* [**`export_for_web`** [#169]](#export_for_web-169)
	* [**`keypress`** [#204]](#keypress-204)
	* [**`take_screenshot`** [#214]](#take_screenshot-214)


&nbsp;

--------
# **Render**




&nbsp;
## **`__init__`** [#26]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/render.py#L26) online

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

- 'format' -> str, 'png', 'svg' or 'jpg'

- scale -> float, values > 1 yield higher resultion screenshots

:param use_default_key_bindings: if True the defualt keybindings from
    vedo are used, otherwise

a custom function that can be used to take screenshots with the
    parameter above.

```

&nbsp;
## **`apply_render_style`** [#97]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/render.py#L97) online

```python
def apply_render_style(self):
```

&nbsp;  
docstring:

no docstring

&nbsp;
## **`render`** [#111]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/render.py#L111) online

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
## **`close`** [#166]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/render.py#L166) online

```python
def close(self):
```

&nbsp;  
docstring:

no docstring

&nbsp;
## **`export_for_web`** [#169]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/render.py#L169) online

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
## **`keypress`** [#204]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/render.py#L204) online

```python
def keypress(self, key):
```

&nbsp;  
docstring:

no docstring

&nbsp;
## **`take_screenshot`** [#214]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/render.py#L214) online

```python
def take_screenshot(self):
```

&nbsp;  
docstring:

no docstring