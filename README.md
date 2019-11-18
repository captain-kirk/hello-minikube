# hello-minikube
spinning up a simple web server using minikube

Follow these steps to complete this project:

https://kubernetes.io/docs/tasks/tools/install-minikube/
https://kubernetes.io/docs/tutorials/hello-minikube/

mkdir hello-minikube
cd hello-minikube
git init
vi server.js
vi Dockerfile

brew install minikube
brew install hyperkit

# Set hyperkit as the default driver 
minikube config set vm-driver hyperkit
minikube start

# Open Kubernetes dashboard in browser
minikube dashboard

# Get pod states 
kubectl get po -A 

# Create a Deployment that manages a Pod
kubectl create deployment hello-node --image=gcr.io/hello-minikube-zero-install/hello-node

# Check deployments
kubectl get deployments

# Get all pods
kubectl get pods

# View cluster events
kubectl get events

# View cluster configuration 
kubectl config view

# Open pod to the public internet
kubectl expose deployment hello-node --type=LoadBalancer --port=8080

# Run your service
minikube service hello-node
