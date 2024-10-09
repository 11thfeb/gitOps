```shell
kind create cluster --config=kind.yaml --name=ch02
```

```shell
helm repo add argo https://argoproj.github.io/argo-helm
```

```shell
$ kubectl create namespace argocd
$ helm install ch02 --namespace argocd argo/argo-cd
```

```shell
$ kubectl port-forward service/ch02-argocd-server -n argocd 8080:443
```

```shell
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d
```