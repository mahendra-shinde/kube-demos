## ConfigMap Demo

1. Create a namespace with your name

    ```
    $ kubectl create namespace mahendra
    ```

2.  Create a new ConfigMap 'config1.yml'

    ```yml
    apiVersion: v1
    kind: ConfigMap
    metadata:
        name: cm1
        ## Set namespace
        namespace: mahendra

    data:
        MYSQL_DATABASE: sampledb
        MYSQL_USER: mahendra
        MYSQL_PASSWORD: pass!1234
        MYSQL_ROOT_PASSWORD: Pass!6778
    ```

3.  Create/Deploy Config map

    ```
    $ kubectl apply -f config1.yml
    ```

4.  View the ConfigMap (namespace is refered as '-n' )

    ```
    $ kubectl get cm cm1 -n mahendra
    $ kubectl describe cm cm1 -n mahendra
    ```

5.  Create a new POD 'test-pod.yml'

    ```yml
    apiVersion: v1
    kind: Pod
    metadata:
        name: testpod
        namespace: mahendra
        labels:
            name: testpod
    spec:
        nodeSelector:
            kubernetes.io/os: linux 
        containers:
        - name: testpod
            image: mysql:5.7
            envFrom:
                - configMapRef:
                    name: cm1
            ports:
            - containerPort: 3306
    ```

6.  Deploy the TEST POD

    ```
    $ kubectl apply -f test-pod.yml
    $ kubectl get pod -n mahendra
    ```

7.  Validate the environment variables from POD

    ```
    $ kubectl exec -n mahendra -it testpod bash
    $ echo $MYSQL_USER
    $ echo $MYSQL_DATABASE
    ```
