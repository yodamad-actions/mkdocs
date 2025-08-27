# mkdocs

A GitHub actions to deploy your [MkDocs](https://www.mkdocs.org/) documentation on GitHub pages.

## Prerequisites

* GitHub Pages must be enabled on your project and setup on `GitHub Actions`

![GitHub Pages configuration](github_pages_config.png)

* Don't forget to add the permissions in your workflow file, as showed in [example](#samples)

```yml
permissions:
  contents: read
  pages: write       # required by deploy-pages
  id-token: write    # required by deploy-pages
```

## Inputs

| Input | Description | Default value |
|-------|-------------|---------------|
| output-dir | Directory containing the static site output | public |
| workdir | Directory containing `main.sdf` slidesk file | . |

## Samples

### Default configuration

```yml
name: Deploy with MkDocs
on:
  push:
    branches: [ "main" ]

## Very important
permissions:
  contents: read
  pages: write       # required by deploy-pages
  id-token: write    # required by deploy-pages

jobs:
  slidesk:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4

      - name: Build & Deploy
        uses: yodamad-actions/mkdocs@1.0.0
```

### All options overriden


```yml
name: Deploy with MkDocs
on:
  push:
    branches: [ "main" ]

## Very important
permissions:
  contents: read
  pages: write       # required by deploy-pages
  id-token: write    # required by deploy-pages

jobs:
  slidesk:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4

      - name: Build & Deploy
        uses: yodamad-actions/mkdocs@1.0.0
        with:
          output-dir: public
          workdir: mkdocs
```
