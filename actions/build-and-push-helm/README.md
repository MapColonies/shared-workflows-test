# Build and Push Helm Chart Action

This GitHub Action packages a Helm chart and pushes it to a Azure Container Registry.

## 🛠 Inputs

| Name         | Description                                                                                   | Required | Default                |
|--------------|-----------------------------------------------------------------------------------------------|----------|------------------------|
| `team`      | The image's team owner (e.g. `3d`, `infra`).                      | ✅ Yes   |                    |
| `context`    | Relative path to the Helm chart directory                                                     | ❌ No   | `./helm`               |
| `registry`   | OCI registry URL where the chart will be pushed (e.g. ACR address)                            | ✅ Yes   |                       |


## 📤 Outputs

| Name    | Description                      |
|---------|----------------------------------|
| `chart` | Name of the Helm chart           |
| `ver`   | Version of the Helm chart        |

## 🚀 Usage

```yaml
- name: Artifactory Login
  uses: MapColonies/shared-workflows/actions/artifactory-login@artifactory-login-v1
  with:
    registry: ${{ secrets.ACR_URL }}
    username: ${{ secrets.ACR_PUSH_USER }}
    password: ${{ secrets.ACR_PUSH_TOKEN }}

- name: Build and Push Helm Chart
  uses: MapColonies/shared-workflows/actions/build-and-push-helm@build-and-push-helm-v1
  with:
    context: ./infra/monitoring
    scope: infra
    registry: ${{ secrets.ACR_URL }}
```
