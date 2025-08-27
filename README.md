# mkdocs

A GitHub actions to deploy your [MkDocs](https://www.mkdocs.org/) documentation on GitHub pages.

## Prerequisites

* GitHub Pages must be enabled on your project and setup on `GitHub Actions`

![GitHub Pages configuration](github_pages_config.png){height=200}

* Don't forget to add the permissions in your workflow file, as showed in [example](#very-important)

```yml
permissions:
  contents: read
  pages: write       # required by deploy-pages
  id-token: write    # required by deploy-pages
```

## Inputs

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


