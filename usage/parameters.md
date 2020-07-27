# Parameters

`brainrender` was designed to be as flexible as possible to allow you to achieve exactly the look you want for your renderings. For this reason, there's a lot of parameters that you can tweak to change `brainrender`'s behavior. 

These are listed in `brainder.default_variables` where you can also find a brief description of what they do. Here's a few of the crucial ones:

```text
DEFAULT_ATLAS: default braninglobe atlas used for the `Atlas` class
WHOLE_SCREEN: if true renderings are shown in full screen
BACKGROUND_COLOR: color of the rendering's background
SHOW_AXES: if True XYZ axes are shown in the rendering
ROOT_COLOR/ROOT_ALPHA: appearance of brain's root mesh
SHADER_STYLE: look of rendered object
SCREENSHOT_TRANSPARENT_BACKGROUND: if true screenshots will 
        be saved with a transparent background
```

### Changing parameters values

There's two ways to change the values of parameters. 

For a quick change, at the beginning  of your `.py` script or Jupyter notebook you can add:

```python
import brainrender
brainrender.PARAM_NAME = param_value
```

e.g.: `brainrender.SHADER_STYLE = "cartoon"`

For a more permanent change, you can edit the `config.yaml` file saved in your `.brainrender` folder. Parameter values will be read from `config.yaml` so editing it will ensure that for all scenes you will create in the future the desired values are read. 

