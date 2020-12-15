# fluentd-kube-nodeport
It is nodeportservice of kubernetes and moves fluentd

## architecture
![test](https://user-images.githubusercontent.com/74946073/102186666-4c6cae80-3ef6-11eb-9309-3807517218e5.png)


## setup
### Create a working directory
use this directory to build a Docker image.This example names the project directory as test
```
mkdir fluentd-kube-nodeport
cd fluentd-kube-nodeport
svn export https://github.com/akiyajma/fluentd-kube-nodeport.git/trunk/
```

### Build image
Use docker build command to build the image. This example names the image as XXX:latest.
```
docker build -t XXX:latest ./
```

### deploy
deploy to kubernetes cluster
```
cd trunk/manifest
kubectl apply -f fluent-conf-configmap.yaml
kubectl apply -f fluentd.yaml
```
### options
The contents of fluent.conf set it in fluent-conf-configmap.The configuration file is stored in the volume of kubernetes.[details.](https://kubernetes.io/docs/tasks/configure-pod-container/configure-pod-configmap/)

