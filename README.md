# Chengyan Zhao's website

This repository contains my Quarto website, including computational posts
analyzing Palmer Penguins data in R and Python. 
The topic is: How does body mass vary among the three penguin species in the Palmer Penguins dataset?

## Requirements

Install these before building:

- Quarto **[1.10.18]**
- uv **[0.12.6]**
- R 4.6.1
- Git

The project pins its Python version in `.python-version` and Python packages
in `uv.lock`. R packages are pinned in `renv.lock`; the committed `renv`
bootstrap files set up renv for the project.

## Build the website

Run these commands in a terminal:

```bash
git clone https://github.com/chengyanzhao289/chengyanzhao289.github.io.git
cd chengyanzhao289.github.io
uv sync --locked
R -e 'renv::restore(prompt = FALSE)'
uv run quarto render
```

Run all commands after `cd` from the repository root, where `_quarto.yml` is
located. The built website is in `docs/`. On macOS, open it locally with:

```bash
open docs/index.html
```

On Linux, use `xdg-open docs/index.html`; on Windows, open `docs/index.html`
in a browser.

## Data

Both computational posts use [Palmer Penguins](https://allisonhorst.github.io/palmerpenguins/)
data, collected by Dr. Kristen Gorman and the Palmer Station Antarctica LTER
Program. The data is available under CC0. The R and Python packages include
the data, so rendering does not download a dataset from a URL. The first build
does need internet access to install the packages recorded in the lockfiles.