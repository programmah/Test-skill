# Test-skill

Starter repository created by Codex github-repository-bootstrap skill

## Structure

- `workspace/`: Primary project work area.
- `misc/`: Supporting notes, experiments, and auxiliary files.

## Getting Started

Build the container image:

```bash
docker build -t Test-skill:latest .
```

Run a shell in the image:

```bash
docker run --rm -it -v "$PWD/workspace:/workspace" Test-skill:latest
```
