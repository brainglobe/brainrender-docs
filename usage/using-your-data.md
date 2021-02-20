---
description: Instructions for using your data in brainrender.
---

# Using your data

Brainrender provide `Actor` classes for many commonly-used data types: [Actors](actors.md). However, before you can use brainrender to visualize your data, you'll have to load and process them to put them into a format that brainrender accepts. These are the main steps you'll have to undertake to visualize your data.

{% hint style="info" %}
If your data is saved as mesh data in a .obj, you don't need to do anything  \(provided your data are registered to the atlases\)!   
`Scene.add()` accepts paths to files and takes care of loading/rendering them.
{% endhint %}

You can find a lot of examples in [brainrender's repository](https://github.com/brainglobe/brainrender), some of these are focused on showing how to load and use your data in brainrender.  Head there for more details. 

### Loading the data

Given the popularity of python for scientific research, there are tools to load almost all data formats. These include numpy to load `.npy` files, pandas for `.csv` and `.h` files etc. Brainglobe provides a general porpuse software tool for loading and saving image data:  [imio](https://github.com/brainglobe/imio). You can use imio to load most types of data:

```python
from imio import load
load.load_any('mydata.tif')
```

### Registering the data

To visualize your data in brainrender, it should be registered to the atlases used by the software. If you used tools like [brainreg](https://github.com/brainglobe/brainreg) your data will already be registered and you can skip this step. If not, you will have to transform your data so that their axes match brainrender's.  Brainglobe has [BG-space](https://github.com/brainglobe/bg-space), a software that aims at facilitating the operation of swapping axes around, which can get confusing rapidly otherwise.

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







