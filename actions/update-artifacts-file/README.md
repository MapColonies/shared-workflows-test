# 📦 Build and Push Helm Chart Action

This GitHub Action builds and publishes a Helm chart to a specified registry and updates an `artifacts.json` metadata file using custom shell scripts. 

---

## 🚀 What It Does

- Checks out the Helm chart repository
- Runs a script to update `artifacts.json` with the chart version and metadata
- Commits and pushes the updated metadata file to the repository

---

## 🔧 Inputs

| Name             | Description                                                                 | Required | Default         |
|------------------|-----------------------------------------------------------------------------|----------|-----------------|
| `scope`          | The directory name used as a logical scope for the artifact                | ✅ Yes   | `""`            |
| `repository`     | GitHub repository that contains the `artifacts.json` file                  | ❌ No    | Current repo    |
| `context`        | Path to the directory containing the Helm chart and helper scripts         | ✅ Yes   | `./helm`        |
| `registry`       | Registry URL the artifact is pushed to (e.g., ACR address)                 | ✅ Yes   | —               |
| `type`           | Type of artifact (`helm`, `docker`, etc.)                                  | ✅ Yes   | `docker`        |
| `artifact_name`  | Name of the artifact (e.g. `sftpgo`, `minio`)                              | ✅ Yes   | —               |
| `artifact_tag`   | Tag or version of the artifact (e.g. `v1.2.3`, `latest`)                   | ✅ Yes   | —               |
| `github_token`   | GitHub token with permission to commit & push changes                      | ✅ Yes   | —               |

---

## ✨ Usage

```yaml
- name: Update artifacts.json
  uses: ./actions/update-artifacts-file
  with:
    context: actions/update-artifacts-file
    scope: infra
    repository: ${{ env.action_repo }}
    artifact_name: "sftpgo"
    artifact_tag: "v2.0.2"
    registry: ${{ secrets.ACR_URL }}
    github_token: ${{ secrets.GH_PAT }}
```
