# Helm Chart Repository

This repository automatically publishes Helm charts to GitHub Pages using GitHub Actions.

## Using the Helm Repository

Once the workflow runs successfully, you can add this repository as a Helm repository and install the chart:

```bash
# Add the Helm repository
helm repo add paperless-ngx https://amphineko.github.io/helm-paperless-ngx/

# Update your Helm repositories
helm repo update

# Install the chart
helm install my-paperless paperless-ngx/paperless-ngx

# Or install with custom values
helm install my-paperless paperless-ngx/paperless-ngx -f my-values.yaml
```

## Chart Development

The chart is automatically packaged and published when:

1. Changes are pushed to the `main` branch that affect:
   - `Chart.yaml`
   - `values.yaml` 
   - Files in `templates/`

2. A new release is published on GitHub

3. The workflow is manually triggered

## Repository Structure

- `Chart.yaml` - Chart metadata and version
- `values.yaml` - Default configuration values
- `templates/` - Kubernetes resource templates
- `.github/workflows/release.yml` - GitHub Actions workflow for publishing
- `cr.yaml` - Configuration for chart-releaser-action

The published charts and repository index are hosted on the `gh-pages` branch and served via GitHub Pages.