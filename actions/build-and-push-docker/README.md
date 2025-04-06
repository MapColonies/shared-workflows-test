# Build and Push Docker Image Action

This GitHub Action builds a Docker image from a specified context and pushes it to a given container registry.

## 🛠 Inputs

| Name         | Description                                                                 | Required | Default                        |
|--------------|-----------------------------------------------------------------------------|----------|--------------------------------|
| `context`    | Path to the Docker build context (e.g. `.` or `./app`).                     | ✅ Yes   | —                              |
| `repository` | Full GitHub repository name. Used for image name.                           | ❌ No    | `${{ github.repository }}`     |
| `team`      | The image's team owner (e.g. `3d`, `infra`).         | ✅ Yes   | —                              |
| `registry`   | Registry URL (e.g. ACR address).                                            | ✅ Yes   | —                              |


## 🚀 Usage

<!-- x-release-please-start-version -->

```yaml
- name: Artifactory Login
  uses: MapColonies/shared-workflows/actions/artifactory-login@artifactory-login-v1
  with:
    registry: ${{ secrets.ACR_URL }}
    username: ${{ secrets.ACR_PUSH_USER }}
    password: ${{ secrets.ACR_PUSH_TOKEN }}

- name: Build and Push Docker Image
  uses: MapColonies/shared-workflows/actions/build-and-push-docker@build-and-push-docker-v1
  with:
    context: .
    scope: infra
    registry: ${{ secrets.ACR_URL }}
```
<!-- x-release-please-end-version -->
