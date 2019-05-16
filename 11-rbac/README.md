## Create admin service account with clusterrole binding

```
kubectl create serviceaccount simon-admin

kubectl get serviceaccounts simon-admin -o yaml

kubectl -n kube-system get secrets simon-admin-token-4tjmg -o jsonpath="{.data.token}" |base64 --decode

kubectl create -f simon_cluster_role.yaml

kubectl create -f simon_cluster_rolebinding.yaml
```


## Create service account with rolebinding limited to dev namespace

```
kubectl -n dev create serviceaccount simon

kubectl -n dev get serviceaccounts simon -o yaml

kubectl -n dev get secrets simon-token -o jsonpath="{.data.token}" |base64 --decode

kubectl create -f simon_role.yaml

kubectl create -f simon_rolebinding.yaml
```
