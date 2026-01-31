# Simple Python package

[![Publish to PyPI](https://github.com/gperdrizet/simple-python-package/actions/workflows/publish-to-pypi.yml/badge.svg)](https://github.com/gperdrizet/simple-python-package/actions/workflows/publish-to-pypi.yml)

This repository is a minimal template for publishing a small Python package to PyPI using GitHub Actions and trusted publishing.

## Usage

### 1. Set up a trusted publisher on PyPI

1. Create a project on PyPI (or plan to create it on first publish).
2. In PyPI, go to **Project → Publishing → Trusted Publishers**.
3. Add a trusted publisher with these values:
	- **Owner**: your GitHub user or org
	- **Repository**: your repo name
	- **Workflow**: `publish-to-pypi.yml`
	- **Environment**: `pypi`

Do this first, before naming the GitHub repository to determine if your planned name is available on PyPI. The GitHub repo and PyPI project names don't have to match, but it's nice if they do!

### 2. Fork this repo and start a new project

1. Fork this repository.
2. In the fork, open **Settings → General → Template repository** and enable it.
3. Click **Use this template** to create your new project.

### 3. Publish from the new project

1. Update `pyproject.toml`:
	- Set `name` to your package name.
	- Update `version`.
	- Update URLs under `[project.urls]`.
2. Commit and push your changes.
3. Create a GitHub release tag that matches your `version` (e.g., `0.1.0` or `v0.1.0`).
4. The **Publish to PyPI** workflow will build and publish automatically.

If you prefer a manual run, you can trigger the workflow from the **Actions** tab.

## Project structure

```
.
├── .devcontainer/               # Dev container config
├── .git/                        # Local Git metadata
├── .github/                     # GitHub configuration
│   └── workflows/
│       └── publish-to-pypi.yml  # Builds package and publishes to PyPI
├── .gitignore                   # Files and folders Git should ignore
├── LICENSE                      # Package license
├── pyproject.toml               # Package metadata, build system, and dependencies
├── README.md                    # Project overview and setup instructions
├── requirements.txt             # Dev/test dependencies for local usage
├── notebooks/
│   └── lorenz_demo.ipynb        # Example notebook demonstrating the package
└── src/
	└── lorenz.py                # Example module shipped in the package
```
