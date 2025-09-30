[![add-on registry](https://img.shields.io/badge/DDEV-Add--on_Registry-blue)](https://addons.ddev.com)
[![tests](https://github.com/colinstillwell/ddev-site-devkit/actions/workflows/tests.yml/badge.svg?branch=main)](https://github.com/colinstillwell/ddev-site-devkit/actions/workflows/tests.yml?query=branch%3Amain)
[![last commit](https://img.shields.io/github/last-commit/colinstillwell/ddev-site-devkit)](https://github.com/colinstillwell/ddev-site-devkit/commits)
[![release](https://img.shields.io/github/v/release/colinstillwell/ddev-site-devkit)](https://github.com/colinstillwell/ddev-site-devkit/releases/latest)

# DDEV Site Devkit

## Overview

DDEV Site Devkit standardises everyday project tasks across multiple repositories while keeping each project in control of its own logic.

This add-on adds a set of first-class DDEV commands that orchestrate common site workflows such as scaffolding, authentication, build, synchronisation, installation, and testing, as well as switching between development and production modes. Some workflows provide both frontend and backend variants.

The heavy lifting lives in project-owned scripts under `.ddev/site-devkit/site/scripts`, so teams can customise behaviour per project without forking the add-on.

**What you get**
* `site-` commands: each command calls a matching script from your project-owned scripts.
* `devkit` commands: tools you can use directly or from within your project-owned scripts.
* Example scripts are automatically generated in `.ddev/site-devkit/site/scripts`.
* Safe, CI-friendly defaults: idempotent tasks, sensible exit codes, and pass-through arguments for full control.
* Framework agnostic: works with any tech stack.

## Install or update

```bash
ddev add-on get colinstillwell/ddev-site-devkit
ddev restart
```

After installing or updating, commit the changes this add-on makes under `.ddev`. In most cases these are in `.ddev/site-devkit` and `.ddev/commands`.

## Usage

### `devkit` commands

| Command | Description |
| ------- | ----------- |
| `ddev devkit-import-database` | Interactively import an SQL dump into the project database |
| `ddev devkit-run-script` | Run a script on the host or in the web container |

### `site` commands

| Command | Description | Examples |
| ------- | ----------- | -------- |
| `ddev site-build` | Run build tasks | `site-build-backend` and `site-build-frontend` |
| `ddev site-build-backend` | Run backend build tasks | `composer install` |
| `ddev site-build-frontend` | Run frontend build tasks | `npm install` |
| `ddev site-install` | Run installation tasks | New project installs the application; existing project runs `site-build-backend`, `site-sync-backend`, `site-build-frontend` and `site-sync-frontend` |
| `ddev site-mode-development` | Enable development mode | Disable caches, enable verbose logging |
| `ddev site-mode-production` | Enable production mode | Enable caches, aggregate CSS and JS |
| `ddev site-scaffold` | Run scaffolding tasks | Copy required files, set permissions |
| `ddev site-sync` | Run synchronisation tasks | `site-sync-backend` and `site-sync-frontend` |
| `ddev site-sync-backend` | Run backend synchronisation tasks | Database import, public files |
| `ddev site-sync-frontend` | Run frontend synchronisation tasks | Images, compiled CSS and JS |
| `ddev site-test` | Run testing tasks | `site-test-backend` and `site-test-frontend` |
| `ddev site-test-backend` | Run backend testing tasks | Unit, kernel, integration |
| `ddev site-test-frontend` | Run frontend testing tasks | Unit, end to end |

## Resources

* [DDEV Documentation for Add-ons](https://ddev.readthedocs.io/en/stable/users/extend/additional-services/)
* [DDEV Add-ons: Creating, maintaining, testing](https://www.youtube.com/watch?v=TmXqQe48iqE) (part of the [DDEV Contributor Live Training](https://ddev.com/blog/contributor-training))
* [Advanced Add-On Techniques](https://ddev.com/blog/advanced-add-on-contributor-training/)
* [DDEV Add-on Maintenance Guide](https://ddev.com/blog/ddev-add-on-maintenance-guide/)

## Contributing

1. Work from an issue. If none exists, create one first.
2. Branch from `main` using `issue/<number>-<short-slug>` in lowercase with hyphens.
3. Make your changes and commit with the prefix `[<number>]`.
4. Add or update tests in `tests` as needed.
5. Update `README.md` as needed.
6. Push your branch and open a pull request on [GitHub](https://github.com/colinstillwell/ddev-site-devkit).

## Testing branch or PR

```bash
# Branch
ddev add-on get https://github.com/colinstillwell/ddev-site-devkit/tarball/<branch>

# Pull request
ddev add-on get https://github.com/colinstillwell/ddev-site-devkit/tarball/refs/pull/<pr-number>/head
```

## Release

Create a [release](https://docs.github.com/en/repositories/releasing-projects-on-github/managing-releases-in-a-repository) on [GitHub](https://github.com/colinstillwell/ddev-site-devkit):
* `main` as the target.
* Follow semantic versioning (`MAJOR.MINOR.PATCH`):
  * `MAJOR`: incompatible changes.
  * `MINOR`: backwards compatible feature additions.
  * `PATCH`: backwards compatible fixes.
* Concise notes.

## Credits

**Contributed and maintained by [@colinstillwell](https://github.com/colinstillwell)**
