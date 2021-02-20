# Actors

Everything rendered in `brainrender` is first used to create an instance of `brainrender`'s `Actor` class. This class handles the 3D mesh data for the object to be rendered and provides a few useful methods for the behind-the-scenes work necessary to render your data. 

While a general `Actor` class can be used to render any type of data that can be used to create a [`vedo Mesh`](https://github.com/marcomusy/vedo) object, several specific `Actor` classes are provided for more conveniently loading commonly used data types.

#### Specific actor classes

* `brainrender.actors.Neuron` is used to render neurons morphology \(e.g. downloaded with `morphapi`\)
* `brainrender.actors.Points` is used to render anything that can be represented as a set of points \(e.g. labelled cells from `cellfinder`
* `brainrender.actors.Streamlines` is used to render streamlines tractography data
* `brainrender.actors.Volume` renders volumetric data \(e.g. gene expression\)
* Other actor classes like `Cylinder`, `Point` and `Ruler` can be used to render other types of data.

In all cases an `actor` instance can be created by passing the data to be rendered to the dedicated `Actor` class. For instance, to render the position of labelled cells, a Nx3 numpy array with the cells coordinates has to be passed to the `Points` class to create an actor representing the cells' locations. 



#### Visualizing other types of data

While the provided `Actor` classes should support the vast majority of users' needs, occasionally you might need to render an unsupported type of data: read [here](using-your-data/) to learn how. 



#### Adding actors to your scene

Rendering actors is as simple as can be: just use the `Scene.add` method and pass to it the actors you would like to see added to your rendering. 

