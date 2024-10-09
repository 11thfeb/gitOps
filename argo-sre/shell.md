```shell
kustomize build . | kubectl apply -f -
```

```shell
kubectl port-forward svc/argocd-server -n argocd 8085:80
```

```shell
kubectl apply -f argocd-app.yaml -n argocd
```

```shell
kubectl rollout restart -n argocd deployment argocd-repo-server
```