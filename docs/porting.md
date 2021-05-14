# Project Porting Guide

_This guide walks you through the process of migrating an existing project to the Singer SDK._

## Poetry Setup (Optional)

We recommend using [`Poetry`](https://python-poetry.org/) for package management. This step is optional but it should also
streamline other parts of the migration process.

Install `pipx` and `poetry`:

```bash
pip3 install pipx
pipx ensurepath
pipx install poetry
```

Initialize [`poetry`](https://python-poetry.org/) inside your existing project:

```bash
cd tap-<myproject>
poetry init
# poetry will setup your project interactively
```

Add `singer-sdk` as a dependency:

```bash
poetry add singer-sdk
```

Or to use a prerelease version of `singer-sdk` you can modify `pyproject.toml` as follows:

```toml
[tool.poetry.dependencies]
python = "^3.8"
singer-sdk = { git = "https://gitlab.com/meltano/singer-sdk.git", branch = "development" }
```

Then:

```bash
poetry install
```