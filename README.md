Action Store
============
This repository contains ready to use github workflows definitions.

## 🔖 Workflows

To reuse this actions you need to create github workflow file inside your targeted repository, you need also pass Private Access Token.

Ready to use workflows:

- [`Building Docker`](.github/workflows/building_docker.yml)
- [`Tagging Semver`](.github/workflows/tagging_semver.yml)

## ⚡ Actions

Particular actions from which final workflows are composed.

  - [building/docker/github](.github/actions/building/docker/github/action.yml)
  - [linting/docker/hadolint](.github/actions/linting/docker/hadolint/action.yml)
  - [tagging/semver/major](.github/actions/tagging/semver/major/action.yml)
  - [tagging/semver/minor](.github/actions/tagging/semver/minor/action.yml)
  - [tagging/semver/patch](.github/actions/tagging/semver/patch/action.yml)

##  🔴 Actions - Tagging Semver

Versions have the format `<MAJOR>.<MINOR>(.<PATCH>)?` where:

- `<MAJOR>` Triggered manualy from default branch,
- `<MINOR>` Triggered automaticly after each push from default branch,
- `<PATCH>` Triggered automaticly after each push from fix/[0-9].[0-9].x branch.

##  🟡 Actions - Building Docker Github

Building job and pushing docker artifact to github ocr requires:

- `token` GitHub Token used to authenticate against a repository for Git context (default ${{ github.token }}),
- `context` Build's context is the set of files located in the specified PATH or URL (default Git context),
- `file` Path to the Dockerfile. (default {context}/Dockerfile)
