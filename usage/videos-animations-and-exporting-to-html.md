# Videos, animations and exporting to html

A key goal for `brainrender` was to facilitate the dissemination of neuroanatomical data. To do so, creating spectacular renderings is not enough, you need to have a way to export them into a format that you can easily share. For this reason we've put a lot of effort into allowing you to do just that. After creating a rendering you can export your work by:

* taking a [**screenshot**](videos-animations-and-exporting-to-html.md#screenshots)\*\*\*\*
* creating an **animated video**
* exporting your scene to an **html file** to share an interactive visualization on the web. 



#### Screenshots

The `Scene` class has a `take_screenshot` method that allows you to save a `.png` image showing the current view of the rendering.  By default the screenshots are saved in `.brainrender/Output/Screenshots`, but you can specify an alternative destination using the `screenshot_kwargs` argument when creating the `Scene`. 

You can use `screenshot_kwargs` to specify:

* `folder`: the folder where the screenshots will be saved 
* `name`: the name that of the `.png` file \(a timestamp will be added\)
* `scale`: larger values result in larger, higher definition, image. 

By default `brainrender` is setup to ignore the background when saving the screenshots. That means that you will have all of your rendered objects in your image, but the background will be transparent. If you want to include the background in your image, include these two lines before creating the screenshot:

```python
import brainrender
brainrender.SCREENSHOT_TRANSPARENT_BACKGROUND = False
```

{% hint style="info" %}
You can also quickly take a screenshot by pressing the "s" key on your keyboard while interacting with the scene!
{% endhint %}





