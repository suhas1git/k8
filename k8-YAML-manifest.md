#### Create Pod YAML

```
kubectl run mypod --image=nginx:latest \
              --labels type=web \
            --dry-run=client -o yaml > mypod.yaml
```

### Create a Pod service YAML

```
kubectl expose pod mypod \
    --port=80 \
    --name mypod-service \
    --type=NodePort \
    --dry-run=client -o yaml > mypod-service.yaml
```

### Create NodePort Service YAML

```
kubectl create service nodeport mypod \
    --tcp=80:80 \
    --node-port=30001 \
    --dry-run=client -o yaml > mypod-service.yaml
```
### Create Deployment YAML

```
kubectl create deployment mydeployment \
    --image=nginx:latest \
    --dry-run=client -o yaml > mydeployment.yaml

```

### Create Deployment Service YAML

```
kubectl expose deployment mydeployment \
    --type=NodePort \
    --port=8080 \
    --name=mydeployment-service \
    --dry-run=client -o yaml > mydeployment-service.yaml
```
### Create Job YAML

```
kubectl create job myjob \
    --image=nginx:latest \
    --dry-run=client -o yaml
```

### Create Job YAML

```
kubectl create cj mycronjob \
    --image=nginx:latest \
    --schedule="* * * * *" \
    --dry-run=client -o yaml
```









