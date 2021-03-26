<br/>
## Start PTP internship project<br/>
### make sure images are available at dockerhub <br/>
- 17ceuog074<br/>
  - ptp-front-end<br/>
  - ptp-nack-end<br/>
>W:\Pirimid\Git Repositories\ptp\ptp-K8s-yaml-files>kubectl create -f . <br/><br/>
configmap/env created<br/>
deployment.apps/postgres-db created<br/>
service/postgres-db created<br/>
deployment.apps/ptp-back-end created<br/>
service/ptp-back-end created<br/>
persistentvolumeclaim/ptp-data created<br/>
deployment.apps/ptp-front-end created<br/>
service/ptp-front-end created<br/>
secret/postgres-secret created<br/>
>W:\Pirimid\Git Repositories\ptp\ptp-K8s-yaml-files>kubectl get pods <br/><br/>
NAME                             READY   STATUS     RESTARTS   AGE<br/>
postgres-db-c8f49d5f9-dfkhw      1/1     Running    0          6s<br/>
ptp-back-end-796956c7c6-tp9rz    0/1     Init:0/1   0          6s<br/>
ptp-front-end-657794ffd9-2m2rd   0/1     Init:0/1   0          6s<br/>
>W:\Pirimid\Git Repositories\ptp\ptp-K8s-yaml-files>kubectl get pods <br/><br/>
NAME                             READY   STATUS            RESTARTS   AGE<br/>
postgres-db-c8f49d5f9-dfkhw      1/1     Running           0          11s<br/>
ptp-back-end-796956c7c6-tp9rz    0/1     PodInitializing   0          11s<br/>
ptp-front-end-657794ffd9-2m2rd   0/1     Init:0/1          0          11s<br/>
>W:\Pirimid\Git Repositories\ptp\ptp-K8s-yaml-files>kubectl get pods <br/><br/>
NAME                             READY   STATUS     RESTARTS   AGE<br/>
postgres-db-c8f49d5f9-dfkhw      1/1     Running    0          29s<br/>
ptp-back-end-796956c7c6-tp9rz    1/1     Running    0          29s<br/>
ptp-front-end-657794ffd9-2m2rd   0/1     Init:0/1   0          29s<br/>
>W:\Pirimid\Git Repositories\ptp\ptp-K8s-yaml-files>kubectl get pods <br/><br/>
NAME                             READY   STATUS            RESTARTS   AGE<br/>
postgres-db-c8f49d5f9-dfkhw      1/1     Running           0          50s<br/>
ptp-back-end-796956c7c6-tp9rz    1/1     Running           0          50s<br/>
ptp-front-end-657794ffd9-2m2rd   0/1     PodInitializing   0          50s<br/>
>W:\Pirimid\Git Repositories\ptp\ptp-K8s-yaml-files>kubectl get pods <br/><br/>
NAME                             READY   STATUS    RESTARTS   AGE<br/>
postgres-db-c8f49d5f9-dfkhw      1/1     Running   0          58s<br/>
ptp-back-end-796956c7c6-tp9rz    1/1     Running   0          58s<br/>
ptp-front-end-657794ffd9-2m2rd   1/1     Running   0          58s<br/>
>W:\Pirimid\Git Repositories\ptp\ptp-K8s-yaml-files>kubectl get deployments <br/><br/>
NAME            READY   UP-TO-DATE   AVAILABLE   AGE<br/>
postgres-db     1/1     1            1           66s<br/>
ptp-back-end    1/1     1            1           66s<br/>
ptp-front-end   1/1     1            1           66s<br/>
>W:\Pirimid\Git Repositories\ptp\ptp-K8s-yaml-files>kubectl get services <br/><br/>
NAME            TYPE           CLUSTER-IP       EXTERNAL-IP   PORT(S)          AGE<br/>
kubernetes      ClusterIP      10.96.0.1        <none>        443/TCP          11m<br/>
postgres-db     ClusterIP      10.111.209.149   <none>        5432/TCP         72s<br/>
ptp-back-end    LoadBalancer   10.96.161.188    localhost     8080:30463/TCP   72s<br/>
ptp-front-end   LoadBalancer   10.104.242.160   localhost     3000:31083/TCP   72s<br/>
>W:\Pirimid\Git Repositories\ptp\ptp-K8s-yaml-files>curl localhost:8080/assets <br/><br/>
{"timestamp":"2021-03-26T03:47:27.084+00:00","status":401,"error":"Unauthorized","message":"","path":"/assets"}<br/>
## Stop all resourses<br/>
>C:\Users\Neel>kubectl delete all --all <br/><br/>
pod "postgres-db-c8f49d5f9-dfkhw" deleted<br/>
pod "ptp-back-end-796956c7c6-tp9rz" deleted<br/>
pod "ptp-front-end-657794ffd9-2m2rd" deleted<br/>
service "kubernetes" deleted<br/>
service "postgres-db" deleted<br/>
service "ptp-back-end" deleted<br/>
service "ptp-front-end" deleted<br/>
deployment.apps "postgres-db" deleted<br/>
deployment.apps "ptp-back-end" deleted<br/>
deployment.apps "ptp-front-end" deleted<br/>
## stop configmaps, secrets, persistentvolumeclaim<br/>
>C:\Users\Neel>kubectl delete configmaps env <br/><br/>
configmap "env" deleted<br/>
>C:\Users\Neel>kubectl delete secrets postgres-secret <br/><br/>
secret "postgres-secret" deleted<br/>
>C:\Users\Neel>kubectl delete PersistentVolumeClaim ptp-data <br/><br/>
persistentvolumeclaim "ptp-data" deleted<br/>