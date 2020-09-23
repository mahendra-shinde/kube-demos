## Deploying Image from Private registry

1.  Create the namespace (Ignore if already created!)

    ```
    $ kubectl create namespace mahendra
    ```


2.  Create the registry secret (Ignore if exists)

    ```
    # SINGLE LINE COMMAND (Remove linebreaks)
    $ kubectl create secret docker-registry -n mahendra regsec 
            --docker-username=reg101   
            --docker-password=LKvifJkYiDSHd9sH/5s0sTytXeF0ldxL 
            --docker-server=reg101.azurecr.io
    ```

3.  Deploy the Deployment & Service objects

    ```
    $ kubectl apply -f . 
    $ kubectl get all -n mahendra
    ```

4.  Try Accessing Service using external-ip.

    ```
    $ kubectl get svc -n mahendra
    ```

5.  Use web-browser to access the application

    `http://{EXTERNALIP}/`


## Clean Up

```
$ kubectl delete -f . 
# OPTIONALLY
$ kubectl delete secret -n mahendra regsec
```

