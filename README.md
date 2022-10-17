# ManimCE bugs

## v0.16.0.post0

### Add .svg extension to SVGMobjects

```python
svg = SVGMobject("file.svg")
#                     ----  this is necessary
```

### Assets dir problem with SVG

If you have configured the assets folder, either with the config dictionary or with cfg files, it will not work with SVG files, so you will have to add the path: `SVGMobject("path_to_file/file.svg")`.

That is, if you have this structure:

```
assets
└── file.svg
```

With this config:

```python
config.assets_dir = "./assets/"
```

or this (in the `manim.cfg` file):

```
[CLI]
assets_dir = ./assets/
```

This is **not** going to work:

```python
svg = SVGMobject("file.svg")
```

So you will have to add the path:

```python
svg = SVGMobject("./assets/file.svg")
```

This will be fixed in the next release.
