# Running The Notebooks

Use these commands from a terminal.

## First Setup

```bash
cd /Users/svetoslavnikov/dev/karpathy
```

Moves into this project folder.

```bash
python3 -m venv .venv
```

Creates a local virtual environment in `.venv/`. This keeps the course packages separate from system Python.

```bash
source .venv/bin/activate
```

Activates the virtual environment. After this, `python` and `pip` should point inside `.venv`.

```bash
python -m pip install --upgrade pip
```

Updates `pip`, the Python package installer.

```bash
python -m pip install -r requirements-notebooks.txt
```

Installs the notebook dependencies: Jupyter, NumPy, Matplotlib, PyTorch, SciPy, widgets, and Graphviz Python bindings.

```bash
python -m ipykernel install --user --name karpathy-notebooks --display-name "Python (karpathy)"
```

Registers this virtual environment as a Jupyter kernel named `Python (karpathy)`.

```bash
python -m jupyter lab
```

Starts JupyterLab.

Open:

```text
work/ep01-micrograd/follow_along.ipynb
```

Then select the kernel:

```text
Python (karpathy)
```

## Future Runs

```bash
cd /Users/svetoslavnikov/dev/karpathy
source .venv/bin/activate
python -m jupyter lab
```

## Graphviz Check

Some Micrograd notebooks use:

```python
from graphviz import Digraph
```

The Python package is installed from `requirements-notebooks.txt`, but the system binary `dot` must also exist.

Check it with:

```bash
which dot
```

If it prints nothing, install Graphviz:

```bash
brew install graphviz
```

## Makemore Data

The Makemore notebooks expect a local file named `names.txt` in the directory where the notebook is running.

This project keeps Karpathy's `makemore` repo here:

```text
nn-zero-to-hero__lectures+projects/projects/makemore/
```

The data file is:

```text
nn-zero-to-hero__lectures+projects/projects/makemore/names.txt
```

## Debugging

If a notebook fails with `ModuleNotFoundError`, check which Python it is using:

```bash
which python
python -V
python -m pip -V
python -c "import sys; print(sys.executable)"
```

Those should point inside:

```text
/Users/svetoslavnikov/dev/karpathy/.venv
```
