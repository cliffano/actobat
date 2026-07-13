<!-- BEGIN:AVATAR -->
![Avatar](avatar.jpg)
<!-- END:AVATAR -->

<!-- BEGIN:BADGES -->
[![Build Status](https://github.com/cliffano/actobat/actions/workflows/ci-workflow.yaml/badge.svg)](https://github.com/cliffano/actobat/actions/workflows/ci-workflow.yaml)
<!-- END:BADGES -->

# Actobat

Actobat is a Makefile for building GitHub Actions.
It provides utility targets for validating action metadata, maintaining dotfiles, and managing releases.

Have a look at [examples/](examples/) for example projects of how Actobat can be used.

## Installation

1. Download `src/Makefile-actobat` as the `Makefile` of your project: `curl https://raw.githubusercontent.com/cliffano/actobat/main/src/Makefile-actobat -o Makefile`
2. Create configuration file `actobat.yml` with properties described in [Configuration](#configuration) section
3. Run the available `Makefile` targets described in [Usage](#usage) section

## Configuration

Create Actobat configuration file called `actobat.yml` with contains the following properties:

| Property | Description | Example |
|----------|-------------|---------|
| package_name | The name of the GitHub Action package | `actobatexample` |
| author | The author of the action | `Some Author` |
| generator.component | The generator component type from [generator-github-action](https://github.com/cliffano/generator-github-action) | `github-action` |
| generator.inputs.project_id | The project ID | `actobatexample` |
| generator.inputs.project_name | The project display name | `ActobatExample` |
| generator.inputs.project_desc | The project description | `A sample GitHub Action built by Actobat` |
| generator.inputs.author_name | The author's name | `Some Author` |
| generator.inputs.author_email | The author's email address | `someauthor@example.com` |
| generator.inputs.author_url | The author's web site URL | `https://example.com` |
| generator.inputs.github_id | The GitHub user or organisation ID | `pakkunbot` |
| generator.inputs.github_repo | The GitHub repository name | `actobatexample` |
| generator.inputs.github_token_prefix | Prefix of GitHub token secret used by release workflows | `STUDIO` |

## Usage

The following targets are available:

| Target | Description |
|--------|-------------|
| ci | CI target to be executed by CI/CD tool, validating GitHub Action project |
| stage | Ensure stage directory exists |
| clean | Remove all temporary (staged, generated, cached) files |
| rmdeps | Remove downloaded package dependencies |
| deps | Download package dependencies using Pip |
| deps-upgrade | Upgrade package dependencies using Pip |
| deps-extra-apt | Install extra tools using `apt`: Python [VirtualEnv](https://virtualenv.pypa.io/) and markdownlint |
| update-to-latest | Update Makefile to the latest version tag |
| update-to-main | Update Makefile to the main branch |
| update-to-version | Update Makefile to the version defined in `TARGET_ACTOBAT_VERSION` parameter |
| update-dotfiles | Update the dotfiles with latest from [generator-github-action](https://github.com/cliffano/generator-github-action) |
| update-partials | Update README partial snippets with latest from [generator-github-action](https://github.com/cliffano/generator-github-action) |
| lint | Run lint checks against action and workflow files using [yamllint](https://www.yamllint.com/) |
| release-major | Create a major release using [rtk](https://github.com/cliffano/rtk) |
| release-minor | Create a minor release using [rtk](https://github.com/cliffano/rtk) |
| release-patch | Create a patch release using [rtk](https://github.com/cliffano/rtk) |

## Colophon

Related Projects:

* [generator-github-action](https://github.com/cliffano/generator-github-action) - GitHub Actions generator using Plop
