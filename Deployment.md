# Bootcamp Description

Test-skill bootcamp repository scaffold validation.

## Deploying the Lab

### Prerequisites

- Hardware: NVIDIA GPU-enabled workstation, server, or cloud instance suitable for the selected labs.
- Operating system: Linux environment with NVIDIA drivers installed.
- Containers: Docker with NVIDIA Container Toolkit, or Singularity/Apptainer with NVIDIA GPU passthrough.
- Base dependencies: Git, Python 3, JupyterLab, and access to any datasets required by the notebooks.

### Tested Environment

Validated on an NVIDIA GPU-enabled development environment. Update this section with the exact GPU, driver, CUDA, and container runtime used for final testing.

### Deploying with Container

#### Docker

Build the Docker image:

```bash
docker build -t test-skill:latest .
```

Run JupyterLab from the container:

```bash
docker run --rm -it --gpus all -p 8888:8888 -v "$PWD/workspace:/workspace" test-skill:latest jupyter lab --ip=0.0.0.0 --port=8888 --allow-root --no-browser
```

#### Singularity / Apptainer

Build the image:

```bash
apptainer build test-skill.sif Singularity
```

Run JupyterLab from the image:

```bash
apptainer exec --nv --bind "$PWD/workspace:/workspace" test-skill.sif jupyter lab --ip=0.0.0.0 --port=8888 --no-browser
```

### Deploying with Python

Use this path only when the labs do not require the container image or when you are preparing a lightweight local environment:

```bash
python -m venv .venv
. .venv/bin/activate
python -m pip install --upgrade pip
python -m pip install -r requirements.txt
```

Dataset setup:

Follow the dataset instructions in the relevant lab notebook or place prepared datasets under `workspace/data/`.

### Known Issues

- GPU is not visible inside Docker: verify the NVIDIA driver and NVIDIA Container Toolkit installation, then rerun with `--gpus all`.
- NGC container pulls fail: authenticate with `docker login nvcr.io` and confirm that the container tag in `Dockerfile` is available.
- JupyterLab does not open in the browser: check the terminal output for the token URL and verify that port `8888` is forwarded.
- Dataset files are missing: rerun the dataset setup command or place the required files under `workspace/data/`.
- Permission errors in mounted folders: confirm that the workspace is writable by the container user or adjust the mount path.

## Repository

- Owner: `programmah`
- Default branch: `main`
- Estimated duration: Estimated 2-4 hours. Update this value for the final bootcamp schedule.
