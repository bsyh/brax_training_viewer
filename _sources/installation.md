# Installation

This guide covers installing BraxViewer and its dependencies.

## Prerequisites

- **Python 3.10 or higher** - [Download Python](https://www.python.org/downloads/)
- **Git** - [Install Git](https://git-scm.com/downloads)
- **A package manager** (pip or uv) - [Install pip](https://pip.pypa.io/en/stable/installation/) or [Install uv](https://docs.astral.sh/uv/getting-started/installation/)

## Steps

### (Optional) Using Conda Virtual Environment

1. Install [conda](https://www.anaconda.com/docs/getting-started/miniconda/main)
2. Create a virtual environment: 
    ```bash
    conda create -n virtual_env_name python=3.10
    ```
3. Activate the environment: 
    ```bash
    conda activate virtual_env_name
    ```

### Repository Setup

1. Download the repository
    ```bash
    git clone https://github.com/pal-robotics/brax_training_viewer.git
    ```
2. Change work directory
    ```bash
    cd brax_training_viewer
    ```
3. Initialize submodules

    :::{important}
    This project includes a custom Brax fork as a git submodule that contains additional features needed for the viewer.
    :::

    ```bash
    git submodule update --init --recursive
    ```
4. Choose your preferred method to install dependencies:
    - **[Pip Installation](installation/installation-pip)**: Traditional Python package installation using pip
    - **[UV Installation](installation/installation-uv)**: Fast, modern Python package installation using uv

## Verification

After installation, verify that BraxViewer and brax version:

```bash
python -c "from braxviewer import WebViewer; from brax.training.agents.ppo import train as ppo; import inspect; assert 'render_fn' in inspect.signature(ppo.train).parameters, 'Official Brax detected. Install modified version instead.'"
```

If no error is printed, your installation was successful! If you encounter an error, please refer to the [Troubleshooting Guide](installation/troubleshooting) for solutions.

## Dependencies

- **FastAPI** (≥0.115.13): Web framework
- **Uvicorn** (≥0.34.3): ASGI server
- **WebSockets** (≥15.0.1): Real-time communication
- **asyncio** (≥3.4.3): Async support
- **JAX**: For numerical computations - [Install JAX](https://github.com/google/jax#installation)

    :::{note}
    Install the version compatible for your hardware to accelerate codes.
    :::
- **Brax**: For reinforcement learning environments (included as submodule)

    :::{important}
    This viewer requires the **modified Brax submodule** which contains additional features needed for real-time visualization. **DO NOT** install the official Brax package from PyPI as it is not compatible.
    :::

## Next Steps

After successful installation, proceed to the [Quick Start Guide](quick-start) to begin using BraxViewer.

For additional help, please [open an issue](https://github.com/pal-robotics/brax_training_viewer/issues) on GitHub. 