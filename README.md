# Kubeval for kustomize

A [GitHub Action](https://github.com/features/actions) to run [Kubeval](https://github.com/instrumenta/kubeval) for [Kustomize](https://github.com/kubernetes-sigs/kustomize) build directories

You can use the action as follows:

```yaml
on: push
name: Validate
jobs:
  kubeval:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@master
    - name: validate kubernetes yaml for kustomize
      uses: nakamasato/kubeval-action@kubeval-kustomize
      with:
        dirs: apps/sample-app/overlays/prod,apps/sample-app/overlays/dev
```

By default the action will recursively scan for YAML files and validate them as Kubernetes obejcts. You can configure this with the parameters.

The Kubeval Action has a number of properties which map to the parameters for Kubeval itself. These are
passed to the action using `with`.

| Property | Default | Description |
| --- | --- | --- |
| dirs | . | directories to run `kustomize build` |
