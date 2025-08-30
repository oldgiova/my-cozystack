# Sample apps
Credits to: https://github.com/fluxcd/flux2-kustomize-helm-example/tree/main

## GitOps init

```bash
apiVersion: source.toolkit.fluxcd.io/v1
kind: GitRepository
metadata:
  name: app
spec:
  url: https://github.com/oldgiova/my-cozystack
  ref:
    branch: gitops-cozystack
---
apiVersion: kustomize.toolkit.fluxcd.io/v1
kind: Kustomization
metadata:
  name: my-cozystack
spec:
  sourceRef:
    kind: GitRepository
    name: app
  path: ./gitops/apps/staging
```
