# Scene

The `Scene` class is the focal point of any work using `brainrender`. It's used to add [actors ](../actors.md)to your visualization, to add brain regions meshes \(by interacting with the `Atlas` class\), to render your scene and use it to export images \(using the `Render` class\). Finally, the creation of a `Scene` is the first step towards the generation of [videos and animations](../videos-animations-and-exporting-to-html.md) as well!

Given its integration with[ BrainGlobe's atlasAPI](https://docs.brainglobe.info/bg-atlasapi/introduction), `brainrender` can be used with any atlas supported by the API. The moment when you're creating your `Scene` is when you have a chance to specify which atlas you intend to use by passing `atlas_name='atlas to use'` to `Scene()`.



### Methods 

#### Adding/removing actors

* `add` and `add_brain_regions`    __can be used to add `actors` to your scene or generate new `actors` to represent brain regions, respectively. To fetch brain regions data, `Scene` uses `brainrender.atlas.Atlas` behind the scenes. The atlas class has a few useful methods \(e.g. `Atlas.hierarchy` can be used to visualize a list of all brain regions in the atlas being used\), these can be accessed using `Scene.atlas.x`.
* `get_actors` can be used to get a handle on actors that are already part of the `Scene`.  You can look for actors using either their name  or br\_class \(e.g. streamlines, neurons...\).
* `remove`  can be used to remove any actor from your scene. 
* All actors that are currently in your scene can be found at `Scene.actors` and `Scene.content` can be used to print out an overview of the scene's content.

#### Editing actors

* `add_label` and `add_silhouette` both take actors as inputs and can be used to add a label or a silhouette to your actors. The label is a piece of text that label's the actor's  mesh in your scene, the silhouette is a black outline around your actor which can be used to make it stand out in your visualization.
* `slice` is a special method which can be used to 'cut' the scene's content with a plane \(e.g. imagine a plane going along the mid line of the brain, this can be used to cut all meshes in half\). Several parameters can be passed to `slice` for instance to only cut specific actors. When using `slice`, you can specify which plane to use for the cutting by either passing one of the supported plane names \(sagittal, frontal and horizontal\) or by creating a custom plane. This can be done using `Scene.atlas.get_plane` and specifying the position and normal of the plane.

#### Rendering and exporting

All the code relative to the rendering of your scene is defined in `brainrender.render.Render`, however `Scene` uses `Render` directly, and as such you can access methods like `Render.render` with `Scene.render`.

The central method is obviously `Scene.render`, this creates a window and generates the 3D interactive rendering. When calling `render` you can specify a [camera position ](working-with-cameras.md)you wish to use. 

Additional methods include `screenshots` and `export` \(for exporting .html files with your rendered scene\).

