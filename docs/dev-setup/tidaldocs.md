---
title: TidalDocs Developer Setup
author: Ishaan Sayal
---
TidalDocs is built on top of [MkDocs](https://www.mkdocs.org/) using the [Material for MKDocs](https://squidfunk.github.io/mkdocs-material/) theme. This guide will help you setup the documentation on your developer environment.

It is recommended to use Python to install all of the software needed for the documenation site.
## Installing MkDocs

To install MkDocs, follow the guide [here](https://www.mkdocs.org/getting-started/). In short, if you already have Python installed and configured for your system, all you have to do is run:
```bash title="terminal"
pip install mkdocs
```

Then, you need to install the theme, Material for MkDocs by running the following command:
```bash title="Terminal"
pip install mkdocs-material
```

We also need to install a plugin as well:
```bash title="Terminal"
pip install mkdocs-open-in-new-tab
```

## Writing Documentation

Once you have cloned and opened the TidalDocs repo, it is recommended to edit documentation using [Obsidian](https://obsidian.md/), or a Markdown editor of your choosing. 

In order to display a live preview of the documentation, run the command:
```bash title="Terminal"
mkdocs serve --livereload
```

You can now open the website at [http://localhost:8000](http://localhost:8000), and preview the documentation in real-time as you update. 