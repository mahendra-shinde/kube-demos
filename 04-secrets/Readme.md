# Secrets : The Encoded Configs

## Types of Secrets

1.  Generic Secrets (Name/Value Pairs)
2.  Docker Registry Secrets
3.  TLS Secrets

## Creating Secrets from COMMANDLINE

```
$ kubectl create secret generic -n mahendra secret1 --from-literal="username=mahendra" --from-literal="password=pass@12345"
$ kubectl get secrets -n mahendra
$ kubectl describe secrets -n mahendra
```

## Registry Credentials as SECRET

```
$ kubectl create secret docker-registry -n mahendra regsec --docker-username=reg101 --docker-password=LKvifJkYiDSHd9sH/5s0sTytXeF0ldxL --docker-server=reg101.azurecr.io
$ kubectl delete pod testpod -n mahendra
```

## Create a new pod `test-pod.yml`

```
$ kubectl apply -f test-pod.yml
$ kubectl get po -n mahendra
```

## Deleting a secrets

```
$ kubectl delete -f test-pod.yml
$ kubectl delete secret -n mahendra secret1 regsec
```