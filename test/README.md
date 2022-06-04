# BEGIN KUBERNETES

```sh
kubectl apply -f pv-config.yml
kubectl apply -f pv-claim.yml
kubectl apply -f pv-pod.yml
```

clean up

```sh
kubectl delete -f pv-pod.yml
kubectl delete -f pv-claim.yml
kubectl delete -f pv-config.yml
```
