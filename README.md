# Versionator

Testing repository for versioning using MkDocs and mike

- MkDocs Material Theme: https://squidfunk.github.io/mkdocs-material/
- mike: https://github.com/jimporter/mike

Configuration tutorial: https://squidfunk.github.io/mkdocs-material/setup/setting-up-versioning/

## Tutorial and Notes:

- Created new conda environment: `conda create -n versionator`, activated: `conda activate versionator`
- Installing `mike` and requirements: 

```
pip install mkdocs
pip install mkdocs-material
pip install msgpack
pip install Jinja2 -U
pip install --ignore-installed PyYAML
pip install mike
```

## Activating versions

> **WARNING:** `mike` pushes to `gh-pages` directly. MkDocs will overwrite these changes if you have an action to build `gh-pages`. Remove  actions that push (build) to `gh-pages` before you make any changes!

```
mike deploy 0.1
mike serve
```
`mike serve` will start a localserver: access via `http://localhost:8000/<version number>`, such as

```
 http://localhost:8000/0.1
```

> **NOTE:** Before pushing to `gh-pages` **make sure `gh-pages` does not exist (can easily delete from the GitHub menu)**, then do

```
mike deploy --push 0.1
```

The first version will be pushed to the `gh-pages` branch.

After changes, adding a second version with

```
mike deploy --push 0.2
mike serve
```

Defining defauilt with `mike set-default --push 0.2`

## Saving your changes to github

You can save your changes to github normally at any step, simply ensure that the `.github` folder does not contain any actions towards `gh-pages`.