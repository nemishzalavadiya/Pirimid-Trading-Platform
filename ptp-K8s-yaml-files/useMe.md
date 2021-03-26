## Start PTP internship project
### Make sure images are available at dockerhub 
- Docker_Hub_username
  - ptp-front-end
  - ptp-back-end
  
```cmd
>w:\Pirimid\Git Repositories\ptp\ptp-K8s-yaml-files>kubectl create -f . 
configmap/env created
deployment.apps/postgres-db created
service/postgres-db created
deployment.apps/ptp-back-end created
service/ptp-back-end created
persistentvolumeclaim/ptp-data created
deployment.apps/ptp-front-end created
service/ptp-front-end created
secret/postgres-secret created
```

```cmd
>w:\Pirimid\Git Repositories\ptp\ptp-K8s-yaml-files>kubectl get pods 
NAME                             READY   STATUS     RESTARTS   AGE
postgres-db-c8f49d5f9-dfkhw      1/1     Running    0          6s
ptp-back-end-796956c7c6-tp9rz    0/1     Init:0/1   0          6s
ptp-front-end-657794ffd9-2m2rd   0/1     Init:0/1   0          6s
```

```cmd
>w:\Pirimid\Git Repositories\ptp\ptp-K8s-yaml-files>kubectl get pods 
NAME                             READY   STATUS            RESTARTS   AGE
postgres-db-c8f49d5f9-dfkhw      1/1     Running           0          11s
ptp-back-end-796956c7c6-tp9rz    0/1     PodInitializing   0          11s
ptp-front-end-657794ffd9-2m2rd   0/1     Init:0/1          0          11s
```

```cmd
>w:\Pirimid\Git Repositories\ptp\ptp-K8s-yaml-files>kubectl get pods 
NAME                             READY   STATUS     RESTARTS   AGE
postgres-db-c8f49d5f9-dfkhw      1/1     Running    0          29s
ptp-back-end-796956c7c6-tp9rz    1/1     Running    0          29s
ptp-front-end-657794ffd9-2m2rd   0/1     Init:0/1   0          29s
```

```cmd
>w:\Pirimid\Git Repositories\ptp\ptp-K8s-yaml-files>kubectl get pods 
NAME                             READY   STATUS            RESTARTS   AGE
postgres-db-c8f49d5f9-dfkhw      1/1     Running           0          50s
ptp-back-end-796956c7c6-tp9rz    1/1     Running           0          50s
ptp-front-end-657794ffd9-2m2rd   0/1     PodInitializing   0          50s
```

```cmd
>w:\Pirimid\Git Repositories\ptp\ptp-K8s-yaml-files>kubectl get pods 
NAME                             READY   STATUS    RESTARTS   AGE
postgres-db-c8f49d5f9-dfkhw      1/1     Running   0          58s
ptp-back-end-796956c7c6-tp9rz    1/1     Running   0          58s
ptp-front-end-657794ffd9-2m2rd   1/1     Running   0          58s
```

```cmd
>w:\Pirimid\Git Repositories\ptp\ptp-K8s-yaml-files>kubectl get deployments 
NAME            READY   UP-TO-DATE   AVAILABLE   AGE
postgres-db     1/1     1            1           66s
ptp-back-end    1/1     1            1           66s
ptp-front-end   1/1     1            1           66s
```

```cmd
>w:\Pirimid\Git Repositories\ptp\ptp-K8s-yaml-files>kubectl get services 
NAME            TYPE           CLUSTER-IP       EXTERNAL-IP   PORT(S)          AGE
kubernetes      ClusterIP      10.96.0.1        <none>        443/TCP          11m
postgres-db     ClusterIP      10.111.209.149   <none>        5432/TCP         72s
ptp-back-end    LoadBalancer   10.96.161.188    localhost     8080:30463/TCP   72s
ptp-front-end   LoadBalancer   10.104.242.160   localhost     3000:31083/TCP   72s
```

```cmd
>w:\Pirimid\Git Repositories\ptp\ptp-K8s-yaml-files>curl localhost:8080/assets 
{"timestamp":"2021-03-26T03:47:27.084+00:00","status":401,"error":"Unauthorized","message":"","path":"/assets"}
```

### Stop all resourses

```cmd
>C:\Users\Neel>kubectl delete all --all 
pod "postgres-db-c8f49d5f9-dfkhw" deleted
pod "ptp-back-end-796956c7c6-tp9rz" deleted
pod "ptp-front-end-657794ffd9-2m2rd" deleted
service "kubernetes" deleted
service "postgres-db" deleted
service "ptp-back-end" deleted
service "ptp-front-end" deleted
deployment.apps "postgres-db" deleted
deployment.apps "ptp-back-end" deleted
deployment.apps "ptp-front-end" deleted
```

### Stop configmaps, secrets, persistentvolumeclaim

```cmd
>C:\Users\Neel>kubectl delete configmaps env 
configmap "env" deleted
```

```cmd
>C:\Users\Neel>kubectl delete secrets postgres-secret 
secret "postgres-secret" deleted
```

```cmd
>C:\Users\Neel>kubectl delete PersistentVolumeClaim ptp-data 
persistentvolumeclaim "ptp-data" deleted
```