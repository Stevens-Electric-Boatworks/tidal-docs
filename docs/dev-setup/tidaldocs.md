---
title: TidalDocs Developer Setup
author: Ishaan Sayal
---
TidalDocs is built on top of [MkDocs](https://www.mkdocs.org/) using the [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/) theme. This guide will help you setup the documentation on your developer environment.

It is recommended to use Python to install all the software needed for the documentation site.
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

### Page Properties

All the documentation pages can have properties assigned to them which can change how they look. The two commonest ones used are `title` and `author`/`authors`. 

If you are using Obisidian, you can type `---`, and Obsidian will automatically create a table where you can insert the required properties. **You must include a title and an author property at the minimum**.
### Creating New Pages

To add a new page, first create a folder and a Markdown file for that specific documentation page. You should then open that file, and create the required properties for that file. To actually make it show up on the documentation, open the `mkdocs.yaml` file, and scroll down to the `nav` section.

From here, you can use `yaml` to describe how the pages should be laid out. For example, if I want to have a tab called "Contributing", with a documentation page called "Code of Conduct", I would have a `nav` section like the following:
```yaml title="mkdocs.yaml"
nav:
# ..., may be more pages
- Contributing:
	- Code of Conduct: contributing/code-of-conduct.md
```

### Adding Images

In order to add an image, you should first put the image inside of the `docs/assets/images` folder. Now, in order to add images, you have to use the Markdown syntax `![alt text here](image path here)`. For example, if you have a folder structure like the following:
```
docs/
├─ assets/images/
│  ├─ cool_image.png
├─ intro/
│  ├─ ...
├─ tidalcore/
│  ├─ ...
├─ contributing/
│  ├─ code-of-conduct.md
```

You will insert the image by inserting the following Markdown:
```markdown title="docs/contributing/code-of-conduct.md"
![Image showcasing cool things](.../assets/images/cool_image.png)
```

This is because you first have to go out of the contributing folder (`...`), and then into the images folder (`/assets/images/`) to get your image. If you do not do this, it may appear to work correctly on Obsidian or even your local dev environment, but will not show up once deployed to production.

## Deploying

!!! note
	Deployment to the `gh-pages` branch has branch protection active which restricts deployment to specific members.

In order to deploy to the production website, you can run:
```bash title="Terminal"
mkdocs gh-deploy
```

This will create a build of the website which will be pushed to the live [docs.stevenseboat.org](https://docs.stevenseboat.org).


## Useful References

[**Material for MkDocs Features Guide**](https://squidfunk.github.io/mkdocs-material/reference/) 

* The Material theme has a lot of features, including both Markdown and general HTML customizations

[**MkDocs User Guide**](https://www.mkdocs.org/user-guide/)

[**Obsidian Markdown Editor**](https://obsidian.md/help/)

[**Markdown Syntax Guide**](https://obsidian.md/help/syntax)