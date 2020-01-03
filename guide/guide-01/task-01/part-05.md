## Deploye Sample Application at Master Node


1. Check deployments

```
kubect get deployments
```

2. Run Nginx Demo

```
kubectl run nginx-demo --image=nginx --port=80
```

3. Check deployments & Service

```
kubect get deployments
kubect get service
```

4. deployments expose

```
kubectl expose deployment nginx-demo --port=80 --type=NodePort
```

5. Check service

```
kubect get service
```

6. Check Server Port

```
kubectl get service
```

7. Check Web page at bro

```
http://master_server_ip:30205
```

