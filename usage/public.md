---
description: How to use brainrender with publicly available datasets
---

# Publicly available datasets

There's some amazing open-science datasets of neuro-atomy out there. You can use them to learn more about your favorite brain region, to plan new experiment or to corroborate the findings of experiments you've already performed. However often interaction with these datasets requires either:

* using dedicated software that comes with the data. 
  * **pros**:  no programming required 
  * **cons:** little room for personalizing renderings and no easy way to integrate with your own data
* learning how to use an API to download the data you need.
  * **pros**: all the flexibility you need
  * **cons:** often requires a time-consuming learning phase \(for each dataset\) and considerable coding skills. 

`brainrender` brings the best of both options together by giving you the **flexibility** of the APIs with a easy to use interface which requires minimal coding skills.

{% hint style="info" %}
**Note:** all publicly available datasets currently supported are based on the Allen Institute altas of the mouse brain. If you know of a cool dataset for a different species that you would like to see supported by `brainrender`, [get in touch](../info/get-in-touch.md)!
{% endhint %}

## Allen Institute Data

`brainrender` can be used to visualize data from many awesome databa sets generated from the Allen Institute \([https://brain-map.org/api/index.html](https://brain-map.org/api/index.html)\). This include the Mouse Brain Atlas, and the Mouse Connectome projects among others. All credit for this data go to the Allen Institute and the Allen Institute's contribution should be aknowledged in any work using this data.

> © 2015 Allen Institute for Brain Science. Allen Brain Atlas API



### Neuroanatomy

`brainrender` relies on brainglobe \[LINK MISSING DOCS\] to get the 3d morphology of brain regions in the mouse atlas \([and others](atlas.md)\). You can use this functionality to render brain regions in your `Scene` which makes contextualizing any other data you might be visualizing easier than ever. 

Head over to the [examples](../overview/examples.md) to see how to implement this in your `Scene`.

### Volumetric gene expression

The Allen measured the spatialized expression levels of many genes in the mouse. They provide a 3d image for each gene showing the expression levels throughout the brain with a resolution of 200µm per voxel.

`brainrender` let's you easily download and visualize the expression levels for your favorite genes:

![](../.gitbook/assets/gene_expr.png)

Head over to the [examples](../overview/examples.md) to see how to implement this in your `Scene`.





### Mouse connectome

#### Tractography

#### Streamlines



## MouseLight project





