# installing brainrender

## Environment

To install `brainrender`, you need a python environment with a `python > 2.7` and `python < 3.8` \(so `3.6` or `3.7` ideally\). If you don't have a python environment ready, you can [crate one](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html) with anaconda.

## Basic installation

Installing `brainrender` is as simple as:

```text
pip install brainrender
```

\(Make sure to have your anaconda environment active when running \`pip install\)

## Advanced installation

If you want the most recent version of `brainrender`'s code, perhaps to help developing it, you can either clone/fork the [github repository](https://github.com/BrancoLab/BrainRender) or you can get it directly from github with:

```text
pip install -U git+https://github.com/BrancoLab/BrainRender.git
```

### Testing installation

To quickly check that everything worked for your installation, try creating a brainrender scene directly from the terminal.

```text
  brainrender TH STR -c
```

This will show a scene based on the `allen mouse atlas` showing the thalamus and the striatum.

