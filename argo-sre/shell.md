## Tạo manifest
Từ thư mục gốc của kho lưu trữ, chạy lệnh sau. Phần đầu tiên, `kustomize build .`, sẽ tạo ra các manifest, trong khi phần thứ hai, `kubectl apply -f -`, sẽ lấy các manifest và áp dụng chúng vào cluster:

```shell
kustomize build . | kubectl apply -f -
```

## Export UI using port-forward
```shell
kubectl port-forward svc/argocd-server -n argocd 8085:80
```

## Apply argocd-app
```shell
kubectl apply -f argocd-app.yaml -n argocd
```

## rollout restart argocd-repo-server để tải cấu hình mới.
```shell
kubectl rollout restart -n argocd deployment argocd-repo-server
```

## Creating the backup
```shell
argocd admin export -n argocd > backup-$(date +"%Y-%m-%d_%H:%M").yml
```

```shell
argocd admin import - < backup-2024-10-11_10:18.yml
```

## Apply argocd-notifications
```shell
kubectl apply -n argocd -f argocd-notifications-app.yaml
```