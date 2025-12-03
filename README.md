# .github

Common reusable GitHub Actions workflows for my projects.

## Workflows

### deploy-docker.yml

A reusable workflow for building and pushing Docker images to GitHub Container Registry (ghcr.io).

**Usage:**

```yaml
name: Deploy to Production

on:
  push:
    branches: [main]

jobs:
  deploy:
    uses: YOUR_USERNAME/.github/.github/workflows/deploy-docker.yml@main
    with:
      app_name: my-app
      dockerfile_path: ./Dockerfile  # optional, defaults to ./Dockerfile
      build_context: .               # optional, defaults to .
```

**Inputs:**

- `app_name` (required): Name of the application/service
- `dockerfile_path` (optional): Path to Dockerfile, defaults to `./Dockerfile`
- `build_context` (optional): Build context directory, defaults to `.`

**Requirements:**

- Repository must have `packages: write` permission
- Uses `GITHUB_TOKEN` for authentication

