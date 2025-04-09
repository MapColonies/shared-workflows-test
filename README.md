# ⚙️ MapColonies Shared GitHub Actions

This repository contains GitHub Actions used across the MapColonies organization, developed and maintained by the **DevOps team**.

> 🧪 The workflows in this repo are primarily for testing and validating the functionality of these actions — **not for general use** in other projects, unless stated otherwise.

---

## 📂 Structure

```
.
├── actions/                # Reusable composite actions
│   ├── artifactory-login/
│   ├── build-docker/
│   ├── build-and-push-helm/
│   ├── helm-lint/
│   ├── eslint/
│   ├── openapi-lint/
│   ├── push-docker/
│   └── update-artifacts-file/
├── test/                   # Assets for testing the actions
├── .github/workflows/      # Utility and Test workflows for each action
├── release-please-config.json
└── README.md
```

Each action has a dedicated folder with:
- `action.yaml` – definition of the action
- `README.md` – usage and inputs specific to the action

---

## 🧪 Purpose of This Repo

- Maintain reusable actions for use in other repositories
- Create test workflows to verify action behavior before tagging
- Manage action versioning and changelogs via `release-please`
- Provide general-use workflows like slash-command triggers

---

## 📦 Actions Included

| Action | Description |
|--------|-------------|
| `artifactory-login`       | Logs in to Azure Container Registry |
| `build-docker`          | Builds Docker images                    |
| `push-docker`           | Pushes Docker images                    |
| `build-and-push-helm`     | Packages and publishes Helm charts |
| `helm-lint`               | Lints and tests Helm charts |
| `eslint`	                | Runs ESLint to check JavaScript/TypeScript code |
| `openapi-lint`            | Validates OpenAPI specs using Redocly CLI |
| `update-artifacts-file`   | Updates `artifacts.json` metadata |

---

## 🧰 Public Workflows

| Workflow        | Purpose                                        |
|----------------|------------------------------------------------|
| `slash-command`| Dispatch slash-command triggered workflows     |
| `postgis-check`| Test DB migrations and compatibility via PR comments |
