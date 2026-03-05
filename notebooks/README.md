# Notebooks

This directory contains Jupyter notebooks for exploration, analysis, and reporting.

## Setup

1. Install dependencies (Python 3.8+):

   ```bash
   pip install jupyter nbstripout
   ```

2. (Recommended) Enable `nbstripout` to automatically strip cell outputs before committing:

   ```bash
   nbstripout --install
   ```

   This installs a git filter that clears outputs and execution counts whenever you stage a notebook, keeping diffs clean and avoiding large output blobs in git history.

   To verify it is active:

   ```bash
   nbstripout --status
   ```

## Running Notebooks

Start the Jupyter server from the repo root:

```bash
jupyter notebook notebooks/
```

Or use JupyterLab:

```bash
jupyter lab notebooks/
```

## Git Hygiene

- `notebooks/.ipynb_checkpoints/` is excluded via `.gitignore` — do not commit checkpoint files.
- If you chose not to install `nbstripout`, clear outputs manually before committing: **Cell → All Output → Clear** (classic Notebook) or **Edit → Clear All Outputs** (JupyterLab).
