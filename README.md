# Versionator

> :warning: **NOTE**: this is not a software, just a guide.

Testing repository for versioning using `MkDocs` and `mike`

- MkDocs Material Theme: https://squidfunk.github.io/mkdocs-material/
- mike: https://github.com/jimporter/mike

Configuration tutorial: https://squidfunk.github.io/mkdocs-material/setup/setting-up-versioning/

---

## Tutorial and Notes:

- Create new conda environment: `conda create -n versionator`, activate: `conda activate versionator`
- Install `mike` and requirements: 

```
pip install mkdocs
pip install mkdocs-material
pip install msgpack
pip install Jinja2 -U
pip install --ignore-installed PyYAML
pip install mike
```

---

## Activating Versions

> :warning: **WARNING:** `mike` pushes to `gh-pages` directly. MkDocs will overwrite these changes if you have an action to build `gh-pages`. Remove  actions that push (build) to `gh-pages` before you make any changes!

```
mike deploy 0.1
mike serve
```
`mike serve` will start a localserver: access via `http://localhost:8000/<version number>`, such as

```
 http://localhost:8000/0.1
```

> :warning: **NOTE:** Before pushing to `gh-pages` **make sure `gh-pages` does not exist (can easily delete from the GitHub menu)**, then do

```
mike deploy --push 0.1
```

The first version will be pushed to the `gh-pages` branch (if `gh-pages` is not present, it will be created automatically).

After changes, add a second version with

```
mike deploy --push 0.2
```

Define default webpage with `mike set-default --push 0.2`.

---

## Saving your changes to GitHub

You can save your changes to GitHub normally at any step, simply ensure that the `.github` folder does not contain any actions towards `gh-pages`.

---

## Branches and Updates

### Branches

`mike` supports deployment from different branches. The correct order of steps is as follows:

1. Deploy webpage with `mike` on `branch <A>` (this could be any branch of your liking).
2. Save your changes to GitHub (add, commit, push) on `branch <A>`.
3. Switch to `branch <B>`.
4. Deploy webpage with `mike` on `branch <B>` (this could be any branch of your liking).
5. Save your changes to GitHub (add, commit, push) on `branch <B>`.

### Updates

You can update a specific version of a `mike` deployed page with `mike deploy <version>` and `mike deploy --push <version>`; prior to pushing with `mike` **ensure that there are no typos in `<version>`**. This will overwrite the specific `mike` deployed version.

Changes and updates can be saved to GitHub normally (add, commit, push).

---

## Example

For a live example, see https://cosimichele.github.io/versionator_mooc/CyVerse-US/.
