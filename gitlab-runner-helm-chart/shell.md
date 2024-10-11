## Thêm Gitlab Helm Repository
```shell
helm repo add gitlab https://charts.gitlab.io
helm repo update
```

## Cấu hình values.yaml (optional)
```shell
gitlabUrl: https://gitlab.com/
runnerRegistrationToken: ******
rbac:
  create: true
```

## Cài đặt GitLab Runner bằng Helm
```shell
helm install gitlab-runner -f values.yaml gitlab/gitlab-runner
```

## check
```shell
kubectl get pods
```

## Update hoặc Xóa GitLab Runner
```shell
## update
helm upgrade gitlab-runner -f values.yaml gitlab/gitlab-runner

## delete
helm uninstall gitlab-runner

```