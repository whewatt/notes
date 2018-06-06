# Kubernetes

See documentation cheat sheet at https://kubernetes.io/docs/reference/kubectl/cheatsheet

### Set project
  
    gcloud config set project whewatt-sandbox

###  Create cluster
    gcloud container clusters create tomcat-cluster --num-nodes=3

### Get credentials for kubectl
    gcloud container clusters get-credentials <cluster name>

### Get Dockerfile from:
	https://github.com/docker-library/tomcat/blob/master/9.0/jre8/Dockerfile

### Build a container
    docker build -t gcr.io/whewatt-sandbox/tomcat:9.0 .

###  Run local container
    docker run -it --rm -p 8888:8080 gcr.io/whewatt-sandbox/tomcat:9.0
  
###  Push to repo
    gcloud docker -- push gcr.io/whewatt-sandbox/tomcat:9.0
  
### Config kubectl
    gcloud container clusters get-credentials NAME --zone ZONE
    gcloud auth application-default login
  
### Deploy an image
    kubectl run tomcat-cluster --image=gcr.io/whewatt-sandbox/tomcat:9.0 --port 8080
    kubectl run tomcat-cluster --image=gcr.io/whewatt-sandbox/tomcat:9.0 --replicas=3 --port 8080
  
### Show nodes
    kubectl get nodes
    kubectl describe nodes <node name> | more
    kubectl get componentstatuses

### Show pods
    kubectl get pods

### Put a load balancer and external IP in front
    kubectl expose deployment tomcat-cluster --type=LoadBalancer --port 8080
  
### What's the IP?
    kubectl get service
  
  
### K8S Dashboard
    gcloud container clusters get-credentials NAME --zone=ZONE --project=PROJECT
    gcloud container clusters get-credentials tomcat-cluster --zone=us-east1-c --project=whewatt-sandbox
    kubectl proxy
    http://localhost:8001/ui

### Cleanup deployment
    kubectl delete service tomcat-cluster
    kubectl delete deployment tomcat-cluster
    gcloud container clusters delete tomcat-cluster

### K8S Services
    kubectl get daemonSets --namespace=kube-system kube-proxy  <doesn't work on GKE>
    kubectl get deployments --namespace=kube-system kube-dns
    kubectl get services --namespace=kube-system kube-dns
    kubectl get deployments --namespace=kube-system kubernetes-dashboard
    kubectl get services --namespace=kube-system kubernetes-dashboard
  
  
### Generate YAML From Running Cluster
    kubectl get all --export=true -o yaml > config.yaml 
  
### Pod Commands
    kubectl run kuard --image=gcr.io/kuar-demo/kuard-amd64:1

    kubectl port-forward <pod> 8080:8080
    http://localhost:8080
  
    kubectl logs <pod>
    kubectl logs -f <pod>
  
    kubectl exec <pod> <os command>
    kubectl exec <pod> ls
  
####  Interactive session
    kubectl exec -it <pod> ash
  
    kubectl cp <pod>:/directory <local file>
  
    kubectl apply -f <yaml>
    kubectl delete pods/<name>
    kubectl delete -f <yaml>
  
    kubectl edit deployment/<deploy name>
    kubectl edit service servicename
