

## Start PTP internship project

### make sure images are available at dockerhub 

- 17ceuog074
  - ptp-front-end
  - ptp-nack-end

W:\Pirimid\Git Repositories\ptp\ptp-K8s-yaml-files>kubectl create -f .
configmap/env created
deployment.apps/postgres-db created
service/postgres-db created
deployment.apps/ptp-back-end created
service/ptp-back-end created
persistentvolumeclaim/ptp-data created
deployment.apps/ptp-front-end created
service/ptp-front-end created
secret/postgres-secret created

W:\Pirimid\Git Repositories\ptp\ptp-K8s-yaml-files>kubectl get pods
NAME                             READY   STATUS     RESTARTS   AGE
postgres-db-c8f49d5f9-dfkhw      1/1     Running    0          6s
ptp-back-end-796956c7c6-tp9rz    0/1     Init:0/1   0          6s
ptp-front-end-657794ffd9-2m2rd   0/1     Init:0/1   0          6s

W:\Pirimid\Git Repositories\ptp\ptp-K8s-yaml-files>kubectl get pods
NAME                             READY   STATUS            RESTARTS   AGE
postgres-db-c8f49d5f9-dfkhw      1/1     Running           0          11s
ptp-back-end-796956c7c6-tp9rz    0/1     PodInitializing   0          11s
ptp-front-end-657794ffd9-2m2rd   0/1     Init:0/1          0          11s

W:\Pirimid\Git Repositories\ptp\ptp-K8s-yaml-files>kubectl get pods
NAME                             READY   STATUS            RESTARTS   AGE
postgres-db-c8f49d5f9-dfkhw      1/1     Running           0          14s
ptp-back-end-796956c7c6-tp9rz    0/1     PodInitializing   0          14s
ptp-front-end-657794ffd9-2m2rd   0/1     Init:0/1          0          14s

W:\Pirimid\Git Repositories\ptp\ptp-K8s-yaml-files>kubectl get pods
NAME                             READY   STATUS            RESTARTS   AGE
postgres-db-c8f49d5f9-dfkhw      1/1     Running           0          18s
ptp-back-end-796956c7c6-tp9rz    0/1     PodInitializing   0          18s
ptp-front-end-657794ffd9-2m2rd   0/1     Init:0/1          0          18s

W:\Pirimid\Git Repositories\ptp\ptp-K8s-yaml-files>kubectl get pods
NAME                             READY   STATUS     RESTARTS   AGE
postgres-db-c8f49d5f9-dfkhw      1/1     Running    0          29s
ptp-back-end-796956c7c6-tp9rz    1/1     Running    0          29s
ptp-front-end-657794ffd9-2m2rd   0/1     Init:0/1   0          29s

W:\Pirimid\Git Repositories\ptp\ptp-K8s-yaml-files>kubectl get pods
NAME                             READY   STATUS     RESTARTS   AGE
postgres-db-c8f49d5f9-dfkhw      1/1     Running    0          34s
ptp-back-end-796956c7c6-tp9rz    1/1     Running    0          34s
ptp-front-end-657794ffd9-2m2rd   0/1     Init:0/1   0          34s

W:\Pirimid\Git Repositories\ptp\ptp-K8s-yaml-files>kubectl get pods
NAME                             READY   STATUS     RESTARTS   AGE
postgres-db-c8f49d5f9-dfkhw      1/1     Running    0          36s
ptp-back-end-796956c7c6-tp9rz    1/1     Running    0          36s
ptp-front-end-657794ffd9-2m2rd   0/1     Init:0/1   0          36s

W:\Pirimid\Git Repositories\ptp\ptp-K8s-yaml-files>kubectl get pods
NAME                             READY   STATUS     RESTARTS   AGE
postgres-db-c8f49d5f9-dfkhw      1/1     Running    0          39s
ptp-back-end-796956c7c6-tp9rz    1/1     Running    0          39s
ptp-front-end-657794ffd9-2m2rd   0/1     Init:0/1   0          39s

W:\Pirimid\Git Repositories\ptp\ptp-K8s-yaml-files>kubectl get pods
NAME                             READY   STATUS            RESTARTS   AGE
postgres-db-c8f49d5f9-dfkhw      1/1     Running           0          50s
ptp-back-end-796956c7c6-tp9rz    1/1     Running           0          50s
ptp-front-end-657794ffd9-2m2rd   0/1     PodInitializing   0          50s

W:\Pirimid\Git Repositories\ptp\ptp-K8s-yaml-files>kubectl get pods
NAME                             READY   STATUS    RESTARTS   AGE
postgres-db-c8f49d5f9-dfkhw      1/1     Running   0          58s
ptp-back-end-796956c7c6-tp9rz    1/1     Running   0          58s
ptp-front-end-657794ffd9-2m2rd   1/1     Running   0          58s

W:\Pirimid\Git Repositories\ptp\ptp-K8s-yaml-files>kubectl get deployments
NAME            READY   UP-TO-DATE   AVAILABLE   AGE
postgres-db     1/1     1            1           66s
ptp-back-end    1/1     1            1           66s
ptp-front-end   1/1     1            1           66s

W:\Pirimid\Git Repositories\ptp\ptp-K8s-yaml-files>kubectl get services
NAME            TYPE           CLUSTER-IP       EXTERNAL-IP   PORT(S)          AGE
kubernetes      ClusterIP      10.96.0.1        <none>        443/TCP          11m
postgres-db     ClusterIP      10.111.209.149   <none>        5432/TCP         72s
ptp-back-end    LoadBalancer   10.96.161.188    localhost     8080:30463/TCP   72s
ptp-front-end   LoadBalancer   10.104.242.160   localhost     3000:31083/TCP   72s

W:\Pirimid\Git Repositories\ptp\ptp-K8s-yaml-files>curl localhost:8080/assets
{"timestamp":"2021-03-26T03:47:27.084+00:00","status":401,"error":"Unauthorized","message":"","path":"/assets"}



## Stop all resourses

C:\Users\Neel>kubectl delete all --all
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

## stop configmaps, secrets, persistentvolumeclaim

C:\Users\Neel>kubectl delete configmaps env
configmap "env" deleted

C:\Users\Neel>kubectl delete secrets postgres-secret
secret "postgres-secret" deleted

C:\Users\Neel>kubectl delete PersistentVolumeClaim ptp-data
persistentvolumeclaim "ptp-data" deleted

