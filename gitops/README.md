# Sample apps
Credits to: https://github.com/fluxcd/flux2-kustomize-helm-example/tree/main

## GitOps init

```bash
export GITHUB_TOKEN=<your-token>
export GITHUB_USER=<your-username>
export GITHUB_REPO=<repository-name>

flux check --pre

flux bootstrap github \
    --context=poc \
    --owner=${GITHUB_USER} \
    --repository=${GITHUB_REPO} \
    --branch=main \
    --personal \
    --path=clusters/poc
```
