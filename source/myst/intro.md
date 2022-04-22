
# Introduction

To use MyST you need to install `myst-parser`
and enable it in Sphinx's {file}`conf.py`:

```
extensions = ["myst_parser"]
```


## Configuration

A number of plugins can be enabled to extend the default syntax.
The way to enable them is to add them to the 
`myst_enable_extensions` list in {file}`conf.py`.

Some of them will be addressed in the [syntax section](syntax.md)
but others are:

- `"smartquotes"`: converts standard quotes to their opening/closing variants
- `"linkify"`: convert bare URLs in hyperlinks


All of them are in the [MyST docs](https://myst-parser.readthedocs.io/en/latest/syntax/optional.html)
