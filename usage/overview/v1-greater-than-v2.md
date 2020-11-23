# V1 -&gt; V2

Brainrender version 2.0 was recently released. This includes a major overhaul of most of `brainrender`'s code and the introduction of a few new features. If you have been using version 1 of `brainrender`, we strongly recommend upgrading to the new one with:

```text
pip install brainrender -U
```

However going from v1 to v2 means that some changes will be needed to make your `brainrender` code work.

### Main changes

#### new Actor class

A new `Actor` class is introduced, everything rendered in `brainrender` is first converted into an instance of `Actor`. Different types of `Actor` class have been created to render different types of data:

* `brainrender.actors.Neuron` is used to render neurons morphology \(e.g. downloaded with `morphapi`\)
* `brainrender.actors.Points` is used to render anything that can be represented as a set of points \(e.g. labelled cells from `cellfinder`
* `brainrender.actors.Streamlines` is used to render streamlines tractography data
* `brainrender.actors.Volume` renders volumetric data \(e.g. gene expression\)
* Other actor classes like `Cylinder`, `Point` and `Ruler` can be used to render other types of data.

The introduction of these new classes implies that the workflow for rendering data in `brainrender` has changed a little bit. While before you would use methods like `Scene.add_cells` to render labelled cells, now you have to create a `Points` actor and add that to the scene with `Scene.add`. The same goes for all other types of visualizations supported by dedicated `Actor` classes. More details can be found in the examples at the [Github repository](https://github.com/brainglobe/brainrender).

If the data you want to render does not have a dedicated `Actor` class, you can create a `vedo` `Mesh` object from your data, as you would've done in v1, and use that to create a generic `Actor` object.

#### changes to Scene class

As state above, most of `Scene`'s method for adding actors to your rendering have been removed. A generic `Scene.add` can be used to add any `Actor` or `Mesh` object to the scene, while `Scene.add_brain_regions` can be used specifically to add brain region meshes. Also methods to add a silhouette or a label to individual actors are supported. 

`Scene` got a few new methods as well: `remove` can be used to remove an `Actor` from the rendering, `get_actors` can be used to get a handle on the actors in the scene. The `slice` method also replaced `cut_actors_with_plane` .

#### changes to Video and new Animation class

The `VideoMaker` class changed slightly. Your interaction with it will be largely unchanged, however its inner workings are now different: it uses `ffmpeg` instead of `opencv` to create and compress videos. This means that you don't need `opencv` anymore \(yay🎉\) however you do need to make sure that `ffmpeg` is installed and working correctly.

A brand new `Animation` class has been introduced which facilitates the creation of videos with more advanced animations, more about it in the docs and examples.

#### the brainrender GUI has landed

The GUI, previously developed as part of a separate python package has not been fully integrated in brainrender.

#### other changes

Much of the remainder of `brainrender`'s functionality persists unchanged. Some method names might have changed however, but you should find all the info you need in the examples at the Github repository.  Two more things worth noticing are:

* The name of the camera parameters used to specify the position of custom cameras have changed
* Some of the parameters in `brainrender.settings` have changed or have been removed.

