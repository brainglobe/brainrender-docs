---
description: Instructions for using your data in brainrender.
---

# Using your data

Brainrender provide `Actor` classes for many commonly-used data types: [Actors](../actors.md). However, before you can use brainrender to visualize your data, you'll have to load and process them to put them into a format that brainrender accepts. These are the main steps you'll have to undertake to visualize your data.

{% hint style="info" %}
If your data is saved as mesh data in a .obj, you don't need to do anything  \(provided your data are registered to the atlases\)!   
`Scene.add()` accepts paths to files and takes care of loading/rendering them.
{% endhint %}

You can find a lot of examples in [brainrender's repository](https://github.com/brainglobe/brainrender), some of these are focused on showing how to load and use your data in brainrender.  Head there for more details. 



## Registering you data

In order to visualize your data in brainrender, it has to be in register with the axes system in brainrender. If you used tools like [brainreg](https://github.com/brainglobe/brainreg) your data will already be registered and you can skip this step. If not, you will have to transform your data so that its axes match brainrender's.  Brainglobe has [BG-space](https://github.com/brainglobe/bg-space), a software that aims at facilitating the operation of swapping axes around, which can get confusing rapidly otherwise. 

Check [Registering data](registering-data.md) for more details.

## Cells coordinates

If you have cells coordinates \(or the coordinates of any other set of points in the brain\) saved in a file \(e.g. as .csv\), you can use many popular python packages for loading them as python arrays. These include pandas for `.csv` and `.h5` files, numpy for `.npy` etc.

## Neuron morphology

Neuron morphologies are generally saved as `.swc` files. Brainrender's `Neuron` class can load morphology data directly from this file format, but head to [morphapi](https://github.com/brainglobe/morphapi) for more details about to load and process neuron morphology data.

## Image data

### Loading the data

Given the popularity of python for scientific research, there are tools to load almost all data formats. These include numpy to load `.npy` files,  `tiffiles` for `.tiff` etc. Brainglobe provides a general purpuse software tool for loading and saving image data:  [imio](https://github.com/brainglobe/imio). You can use imio to load most types of data:

```python
from imio import load
load.load_any('mydata.tif')
```

### volume -&gt; surface

If your data is as volumetric \(3D voxels\) image,  you might want to extract mesh information from your data. If that's the case, `vedo` provides code to go from volumes to meshes:

```python
from vedo import Volume
from brainrender import Scene

vol = Volume(mydata)
mesh = vol.isosurface()

scene = Scene()
scene.add(mesh)
```

Vedo provides many more methods to go from volume to mesh and vice versa: check [its awesome documentation ](https://vedo.embl.es)for more details.

You can also render your data directly as a brainrender `Volume` class: 

```python
from brainrender import Scene, actors
scene = Scene()
scene.add(actors.Volume(mydata))
```

## Streamlines

Brainrender can create streamlines visualizations for connectomics data. Data for streamlines can be saved as `.json` and loaded with pandas's `read_json` function. Data should be organized in a hierarchical structure with two main entries \(`points` and `lines`\) denoting the injection points and the coordinates of points along each "line" of the streamlines.  Each line should be a list of dictionaries with "x", "y" and "z" coordinates.

