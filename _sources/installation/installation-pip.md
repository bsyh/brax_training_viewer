# Pip Installation

This guide covers installing dependencies using pip.

## Installation Steps

1. Install the local Brax submodule
    ```bash
    pip install ./brax
    ```
2. Install braxviewer
    ```bash
    pip install .
    ```
    
    :::{note}
    Use `pip install -e .` for development mode, which creates an editable installation that reflects code changes without reinstallation.
    :::
3. Install dependencies
    ```bash
    pip install -r requirements.txt
    ```

## Optional: Hardware Acceleration

Install JAX with hardware acceleration for improved performance:

```bash
# For CUDA 12
pip install -U "jax[cuda12]"

# For CUDA 11
pip install -U "jax[cuda11]"

# For TPU
pip install -U "jax[tpu]"
```

## Getting Help

If you continue to experience issues:

1. Check the [UV Installation Guide](installation-uv) as an alternative
2. Review the [Troubleshooting Guide](troubleshooting) for common solutions
3. [Open an issue](https://github.com/pal-robotics/brax_training_viewer/issues) on GitHub 