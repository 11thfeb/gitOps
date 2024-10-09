```shell
kustomize build . | kubectl apply -f -
```

```shell
kubectl port-forward svc/argocd-server -n argocd 8085:80
```
