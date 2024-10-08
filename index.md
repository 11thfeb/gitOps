```shell
kubectl create namespace test-imperative
```

```shell
kubectl get namespace test-imperative
```

```shell
kubectl create deployment nginx-imperative --image=nginx -n test-imperative
```

```shell
kubectl get deployment -n test-imperative nginx-imperative
```

```shell
kubectl label namespace test-imperative namespace=imperative-apps
```

```shell
kubectl delete deployment -n test-imperative nginx-imperative
kubectl delete namespace test-imperative
```
