# Using Notebooks

`brainrender` can be used with Jupyter notebooks. When using notebooks you have two options:

1. you want your **rendering embedded** in the notebook
2. you're okay with the rendering being **shown** in a separate pop-up window.

let's see how we can achieve both. 



#### Embedding renderings in Jupyter notebooks

By default `brainrender` is setup to let you embed your renderings in a jupyter notebook, so it's fairly simple to achieve this. 

{% hint style="danger" %}
When embedding renderings in Jupyter Notebook not all of `brainrender`'s functionality will work! If you want to support all of `brainrender`'s features you should **not embed** renderings in the notebooks.
{% endhint %}

As said above, you might not have access to all features when embedding your renderings. That's because of the `k3d` backend used to achieve the embedded renderings. 

In particular `Scene.render()` will prepare the rendering for you, but it won't actually create the render. To visualize your scene you will need a couple extra lines of code:

```text
from vedo import Plotter

vp = Plotter()
show(scene.get_actors())
```



#### Rendering your scene in a separate window

If you've decided to **not** embed your scene in the notebook, then you just need to add a couple lines at the beginning of your notebook:

```text
from vedo import embedWindow
embedWindow(False) 
```

after this everything will work exactly the same as usual, and you _will_ have access to all of `brainrender`'s features!

