---
description: A quick overview of how you can create Scenes from your terminal.
---

# Command Line Interface

Often you want to create a quick `Scene` to look something up in a hurry. Worry not! `brainrender` won't stand in your way. 

`brainrender` comes with a command line option to create simple scenes without even opening your favorite IDE, you can do it all in the terminal. 

The command is very simple:

```text
brainrender
```

but it comes with a few options to make things more interesting. 

### Adding brain regions

You can follow `brainrender` with the acronyms of the brain regions you'd like to add to your `Scene`. For instance say you want to have the thalamus and the striatum to your scene, then:

```text
brainrender STR TH
```

### Changing atlas

You can use the optional argument `-a` to use a brainglobe atlas different from what's set as default:

```text
brainrender TH -a allen_human_500um
```

### Adding data from files

If you have a 3d object saved as a `.obj` or .`stl` file you can use the `-f` argument and pass the path to the file you'd like to include in your `Scene`. 

```text
brainrnder -f path/to/object.obj
```

It also works with `.h5` files with cell coordinates data:

```text
brainrender -f path/to/my/cells.h5
```





