# Data-Analytics

This repository contains the lab materials covered in the Data Analytics module. The repository is organised by week, and each `Week*` folder contains one or more Jupyter notebooks plus any local datasets or images used by those notebooks.

## Repository layout

- `Week1` to `Week10`: tutorial notebooks and the datasets used by each tutorial
- `README.md`: setup and usage guide

## Requirements

This repository now follows a normal `uv` project workflow.

The notebooks in this repository use these Python packages:

- `jupyterlab`
- `ipykernel`
- `pandas`
- `numpy`
- `matplotlib`
- `scipy`
- `scikit-learn`

Python 3.11 or newer is recommended.

## Setup with uv

`uv` is a fast Python package and environment manager. Install it first by following the official installation guide:

- https://docs.astral.sh/uv/getting-started/installation/

Then, from the repository root, sync the project environment:

```powershell
cd C:\Programming\Data-Analytics
uv python install 3.11
uv sync
```

This creates the project virtual environment and installs the dependencies declared in `pyproject.toml`. `uv` will also create or update `uv.lock` when the environment is synced.

Start JupyterLab through the managed `uv` environment:

```powershell
uv run jupyter lab
```

## Running the notebooks

Always start JupyterLab from the repository root so the notebooks can resolve the local datasets correctly:

```powershell
cd C:\Programming\Data-Analytics
uv run jupyter lab
```

Inside JupyterLab:

1. Open the notebook you want to work on.
2. Select the project environment kernel if JupyterLab asks for one.
3. Run cells normally and save your edits in place.

## Managing dependencies with uv

This repository includes a `pyproject.toml`, so package changes should be tracked as project dependencies.

Add a new package:

```powershell
uv add <package-name>
```

Add a development-only package:

```powershell
uv add --dev <package-name>
```

Remove a package:

```powershell
uv remove <package-name>
```

Re-sync the environment after dependency changes:

```powershell
uv sync
```

## Troubleshooting

- If `uv` is not recognised, install it first and restart PowerShell.
- If a notebook cannot find a dataset, make sure JupyterLab was started from `C:\Programming\Data-Analytics`.
- If JupyterLab opens but a notebook kernel is missing, run `uv sync` again to ensure `ipykernel` is installed in the project environment.
- If you prefer to work inside an activated shell, use `.venv\Scripts\Activate.ps1` after `uv sync`, but it is optional when using `uv run`.

## References

- uv installation: https://docs.astral.sh/uv/getting-started/installation/
- uv projects and `uv init`: https://docs.astral.sh/uv/concepts/projects/init/
- uv dependency management: https://docs.astral.sh/uv/concepts/projects/dependencies/
- uv Python management: https://docs.astral.sh/uv/guides/install-python/
- JupyterLab installation: https://jupyterlab.readthedocs.io/en/stable/getting_started/installation.html
