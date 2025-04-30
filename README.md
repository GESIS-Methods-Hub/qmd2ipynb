# GESIS Methods Hub Quarto to Jupyter Notebook as GitHub Action

This is a [GitHub Action](https://github.com/features/actions) to convert a `.qmd` file into a `.ipynb` file and store the new `.ipynb` in the GitHub repository.

## Usage

Create the file `.github/workflows/methods-hub-qmd2ipynb.yml` with

```yaml
name: Convert Quarto to Jupyter Notebook
on:
  push:
    branches:
      - main
    paths:
      - method.qmd
      - tutorial.qmd
jobs:
  convert-qmd-into-ipynb:
    runs-on: ubuntu-24.04
    steps:
      - name: Convert Quarto to Jupyter Notebook
        uses: GESIS-Methods-Hub/qmd2ipynb@v2
        with:
          files: 'method.qmd tutorial.qmd'
          token: ${{ secrets.GITHUB_TOKEN }}
```