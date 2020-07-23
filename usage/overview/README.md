---
description: A brief overview of brainrender's code structure
---

# Overview

{% hint style="info" %}
This section explains the logic behind how `brainrender` works. If you want more details about which classes/methods are part of each script, and what they do, check the automatically generated docs [here]().
{% endhint %}

The key element of any `brainrender` visualisation is the `Scene` class. It defines what you will render and how it should look like. It's counterpart is the `Atlas` class which does most of the 'behind the scenes' work fetching and loading the data you want to look at.

#### Workflow

In most of your renderings these are the steps you will need

1. Create your `Scene`. This is where you specify the general look of your rendering \(e.g. which species' atlas you will be using\).
2. Add new elements to your scene \(e.g. neurons, brain regions, implants...\) and specify how they should look
3. Render, make videos, take screenshots.



When adding new elements \(`actors`\) to your `Scene` you will encounter two situations:

1. You have the data \(e.g. location of labelled cells from [cellfinder](https://docs.cellfinder.info/)\) and you just want to visualize them.
2. You don't have the data but you want to visualize a specific item \(e.g. a brain region in the mouse brain\).



### You have the data

That's great, you've done most of the work. You've done your experiment and run the analysis, now you just want to make a good rendering of your data. Fortunately that's the easy \(and fun\) part! 

For almost anything you might want to visualize  there's a dedicated method in the `Scene` class, so head over [here](../scene.md) to learn more about how `Scene` works. Head over [here](../user.md) for more details about how to render your data. 



### You don't have the data

No worries, there's plenty of available data out there that you can use. Often though these datasets are hard to navigate and the APIs that support them take some learning before you can start using them. 

That's why `brainrender` does all the 'behind the scenes' work for you! If you want data from one of the Allen institute projects, from [neuromorpho](http://neuromorpho.org/) or from Janelia's Mouse Light project, all you have to do is specify what you need. `brainrender` will fetching, download it and render it for you!

While you'll be using `Scene` to do all of this, `Atlas` is where most of this work takes place. So head over [here](../scene.md) to learn more about `Scene` and over [here](../atlas.md) to learn more about `Atlas`. Have a look [here](../public.md) for more details about using publicly available data.



## Using Notebooks

`brainrender` can be used ...

