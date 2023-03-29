## start a k8s cluster & local registry
https://github.com/tilt-dev/ctlptl#minikube-with-a-built-in-registry

```sh
ctlptl create registry ctlptl-registry --port=5005
ctlptl create cluster kind --registry=ctlptl-registry
```

# set a github personal access token
export GITHUB_ACCESS_TOKEN=...

## build & deploy
https://tilt.dev/
```sh
tilt up
```

kubectl patch serviceaccount argo-workflow -p '{"imagePullSecrets": [{"name": "ctlptl-regcred"}]}' -n argo