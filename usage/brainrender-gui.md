# Brainrender GUI

Brainrender now comes with a GUI \(graphical user interface\) for accessing brainrender's functionality without need for writing custom python code.

{% hint style="info" %}
Currently `bg-brainrender-gui` only supports some of `brainrender`'s core functionality, but we are happy to extend `bg-brainrender-gui` should there be interest in this.
{% endhint %}

The source code for `bg-brainrender-GUI` can be found at [Github repository](https://github.com/brainglobe/bg-brainrender-gui) where you can also open issues to ask questions or report bugs.

### Usage

You can **start** `brainrender-gui` directly from your terminal with the command

```text
brainrender-gui
```

Once the GUI is started it will open a window visualizing the `root` mesh of the atlas selected and several buttons to add and remove elements to the `brainrender` scene.

![](../.gitbook/assets/image%20%286%29.png)

{% hint style="success" %}
To s**pecify which atlas to use:** use the **`-a`** argument when calling `brainrender-gui`:

```text
brainrender-gui -a allen_human_500um # the GUI will use the human atlas
```
{% endhint %}

### Adding actors

The first set of buttons is used to add elements to the `brainrender` scene:

* `Add brain regions`: clicking on this button opens a new window where  you can input the names of the brain regions to be added to the brainrender scene. 
* `Add cells`: clicking on this button opens a dialog to select and load a file containing cell coordinates data \(e.g. a `csv` file\). 
* `Add from file`: clicking on this button opens a dialog to select and load a file for a 3d mesh \(e.g. a `.obj` file\). 

### Editing actors

Whenever an actor is added to the scene, its name will be added to the `Actors` list. The list can also be used to edit rendered actors:

* Double clicking an actor's name **will toggle the visibility** of the corresponding mesh. 
* A single click on an actor's name selects it for **editing** with **the `alpha`** \(transparency\) and **`color`** options below the actors list. Once an actor is selected from the `Actors` list, its color and alpha will appear in the text boxes below. Editing the values in these textboxes change the corresponding actor's properties.



### The hierarchy view

Pressing the `Show structures tree` button at the bottom right of the window shows a panel with the hierarchy view of brain regions in the selected atlas: ![](screenshots/app2.png)

![](../.gitbook/assets/image%20%287%29.png)

The hierarchy view can be used to explore the structures hierarchy as well as to add brain regions to the scene: clicking on a region's tick box will add it to the list of actors in the scene. Press the same button again to hide the hierarchy view.



### Taking screenshots

Under the main canvas there is a button that can be used to save a screenshot with the current view of the `brainrender` scene. 

To specify where to save the screenshot, use the `-o` argument when calling `brainrender-gui`:

```text
brainrender-gui -o path/to/screenshots/folder
```



### Camera control

To the right of the screenshots button is a panel of buttons used to set the camera position in the `brainrender Scene:`

* `Reset` resets the camera to what is defined as default in `brainrender` \(i.e. `brainrender.CAMERA`\).
* `Top` moves the camera so that the brain is viewed from the top
* `Side1` and `Side2` move the camera to view the brain from the side \(left and right sides\).
* `Front` moves the camera to view the brain from the front.



