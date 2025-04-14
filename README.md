# oopm-publish-action

this is an action to publish oomol package by github action.

## Prerequisites

this action need `id_token` permission to publish package to github packages.

```yaml
permissions:
  id-token: write
```

## Example

```yaml
name: Publish OOMOL Package
on:
  push:
    branches:
      - main

permissions:
  id-token: write

jobs:
  on: ubuntu-latest
    runs-on: ubuntu-latest
    steps:
      - name: Checkout code
        uses: actions/checkout@v4
      - name: Set up Node.js
        uses: actions/setup-node@v4
      - name: Install oopm
        run: npm install -g oopm
      - name: Publish OOMOL Package
        uses: oomol-lab/oopm-publish-action

```