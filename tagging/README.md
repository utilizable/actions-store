Github Actions - Semver Tagging
============
This repository serves as a semver template for all pojects.

## 🔖 Reusing workflows

To reuse this actions you need to create github actions workflow file inside your targeted repository, you need also pass Private Access Token if you want to trigger workflow for tag.

`./.github/workflows/semver.yml`
```yml
name: semver

on:
  push:
  workflow_dispatch:

permissions:
  contents: write
  pull-requests: write

jobs:
  semver:
    uses: utilizable/github-actions-semver-tagging/.github/workflows/semver.yml@develop
    secrets:
      PAT: ${{ secrets.PAT }}
```

## 🔖 Versioning model

Versions have the format `<MAJOR>.<MINOR>(.<PATCH>)?` where:

- `<MAJOR>` Triggered manualy from default branch,
- `<MINOR>` Triggered automaticly after each push from default branch,
- `<PATCH>` Triggered automaticly after each push from fix/[0-9].[0-9].x branch.
