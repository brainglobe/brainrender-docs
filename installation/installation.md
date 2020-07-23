---
description: Instructions for installing brainrender
---

# Installing brainrender

## Environment

To install `brainrender`, you need a python environment with a `python > 2.7` and `python < 3.8` \(so `python 3.6` or `3.7` ideally\). If you don't have a python environment ready, you can [crate one](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html) with anaconda.

## Basic installation

Installing `brainrender` is as simple as:

```text
pip install brainrender
```

{% hint style="success" %}
Make sure to have your anaconda environment active when running `pip install`
{% endhint %}

{% hint style="warning" %}
You might get some error messages reporting conflicting version requirements for the `allensdk` package and a couple others. You can safely ignore these. 
{% endhint %}

{% hint style="info" %}
Note that some of `brainrender`'s more rarely used features may require the installation of additional packages. 
{% endhint %}

## Advanced installation

If you want the most recent version of `brainrender`'s code, perhaps to help developing it, you can either clone/fork the [github repository](https://github.com/BrancoLab/BrainRender) or you can get it directly from GitHub with:

```text
pip install -U git+https://github.com/BrancoLab/BrainRender.git
```

### Testing installation

To quickly check that everything worked for your installation, try creating a `brainrender` scene directly from the terminal.

```text
  brainrender TH STR -c
```

This will show a scene based on the `allen mouse atlas` showing the Thalamus and the Striatum.

