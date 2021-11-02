# kustomize-consul-k8s

## Pre-requisites

- kustomize
- Helm 3.2+ (see https://github.com/helm/helm/issues/7260)

## Usage

1. Edit `kustomization.yaml` to add patches for each kind you would like to apply a patch to. Ensure that the patch file
includes the patch to add a lablel. 

```
helm install consul-deployment hashicorp/consul --version "0.35.0" --create-namespace -n consul -f ./server-config.yaml --post-renderer ./kustomize-postrenderer.sh  
```