# Working with cameras

The creation of an interactive rendering, or a video, involves the specification of the position and orientation of a "camera" representing your point of view. 

`Brainrender` provides a number of pre-defined cameras that can be used \(e.g. `sagittal` or `frontal`\). If you wish to use any of these cameras just pass the corresponding name to `Scene.render` \(e.g. `scene.render(camera='frontal')`\). `render` also takes a `zoom` parameter which specifies the camera's zoon.

You can, however, create a **custom** camera for your needs by specifying a set of **camera parameters** and pass that \(as a dictionary\) to `scene.render`. To get the parameters you need, the simplest thing is to render your scene with any old camera, move the scene to get the point of view you need and press `c` on your keyboard. This will print out the current camera parameters. You can then close your scene and copy-paste the camera parameters in your code. The next time you render your scene it will use your parameters!

The **parameters** used to specify a camera include:

* `pos`: a set of 3D coordinate specifying the position of the camera
* `viewup`: a 3d vector indicating the direction of "up" in your scene \(should always be `0, -1, 0`\).
* `clippingRange`: a set of a short and long distance, anything outside this range will not be render

additional parameters \(not generally needed\):

* `focalPoint` specifies the 'focal point' of the camera
* `distance` the camera's distance.



