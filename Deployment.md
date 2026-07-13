# Deployment

## Container Image

Build the Docker image:

```bash
docker build -t Test-skill:latest .
```

Run the image:

```bash
docker run --rm -it Test-skill:latest
```

## Singularity / Apptainer

Build from the Singularity definition:

```bash
singularity build Test-skill.sif Singularity
```

Run the image:

```bash
singularity exec Test-skill.sif bash
```

## Repository

Default branch: `main`

Owner: `programmah`
