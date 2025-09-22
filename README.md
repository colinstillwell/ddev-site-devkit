[![add-on registry](https://img.shields.io/badge/DDEV-Add--on_Registry-blue)](https://addons.ddev.com)
[![tests](https://github.com/colinstillwell/ddev-site-devkit/actions/workflows/tests.yml/badge.svg?branch=main)](https://github.com/colinstillwell/ddev-site-devkit/actions/workflows/tests.yml?query=branch%3Amain)
[![last commit](https://img.shields.io/github/last-commit/colinstillwell/ddev-site-devkit)](https://github.com/colinstillwell/ddev-site-devkit/commits)
[![release](https://img.shields.io/github/v/release/colinstillwell/ddev-site-devkit)](https://github.com/colinstillwell/ddev-site-devkit/releases/latest)

# DDEV Site Devkit

## Overview

This add-on integrates Site Devkit into your [DDEV](https://ddev.com/) project.

## Installation

```bash
ddev add-on get colinstillwell/ddev-site-devkit
ddev restart
```

After installation, make sure to commit the `.ddev` directory to version control.

## Usage

| Command | Description |
| ------- | ----------- |
| `ddev describe` | View service status and used ports for Site Devkit |
| `ddev logs -s site-devkit` | Check Site Devkit logs |

## Advanced Customization

To change the Docker image:

```bash
ddev dotenv set .ddev/.env.site-devkit --site-devkit-docker-image="ddev/ddev-utilities:latest"
ddev add-on get colinstillwell/ddev-site-devkit
ddev restart
```

Make sure to commit the `.ddev/.env.site-devkit` file to version control.

All customization options (use with caution):

| Variable | Flag | Default |
| -------- | ---- | ------- |
| `SITE_DEVKIT_DOCKER_IMAGE` | `--site-devkit-docker-image` | `ddev/ddev-utilities:latest` |

## Credits

**Contributed and maintained by [@colinstillwell](https://github.com/colinstillwell)**
