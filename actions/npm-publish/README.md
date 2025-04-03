# 📦 Publish npm Package Action

This GitHub Action installs dependencies, runs a `prepack` script, and publishes a package to the npm registry using
[`npm-publish`](https://github.com/JS-DevTools/npm-publish).

---

## 🛠 Inputs

| Name           | Description                                                        | Required | Default                      |
|----------------|--------------------------------------------------------------------|----------|------------------------------|
| `node-version` | The version of Node.js to use                                      | ❌ No    | `20`                         |
| `npm-token`    | npm authentication token (`NODE_AUTH_TOKEN`)                       | ✅ Yes   | —                            |
| `repository`   | GitHub repository to checkout (useful in reusable workflows)       | ❌ No    | `${{ github.repository }}`   |
| `path`         | Path to the directory containing the `package.json` to publish     | ❌ No    | `.`                          |

---

## 🚀 Usage

```yaml
- name: Publish npm Package
  uses: MapColonies/shared-workflows/actions/publish-npm@v1
  with:
    node-version: '20'
    npm-token: ${{ secrets.NPM_TOKEN }}
```
