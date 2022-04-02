# Versionator

Testing repository for versioning using MkDocs and mike

- MkDocs Material Theme: https://squidfunk.github.io/mkdocs-material/
- mike: https://github.com/jimporter/mike

Configuration tutorial: https://squidfunk.github.io/mkdocs-material/setup/setting-up-versioning/

## Tutorial and Notes:

- Created new conda environment: `conda create -n versionator`, activated: `conda activate versionator`
- Installing `mike` and requirements: 

```
pip install msgpack
pip install Jinja2 -U
pip install --ignore-installed PyYAML
pip install mike
```

## Activating versions

```
mike deploy 0.1
mike serve
```
`mike serve` will start a localserver: access via `http://localhost:8000/<version number>`, such as

```
 http://localhost:8000/0.1
```

Adding a second version with

```
mike deploy 0.2
mike serve
```

Defining defauilt with `mike set-default 0.1`