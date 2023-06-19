# How to deploy the ATM application locally using Minikube 
In this document we will explain the steps necessary to run the whole ATM application within a Minikube cluster. Prerequisites  

## Prerequisites 

- Minikube (https://minikube.sigs.k8s.io/docs/start/) 
- Kubectl (https://kubernetes.io/docs/tasks/tools/) 

 

## Steps 

1. Start a minikube cluster by using the command ```minikube start``` in a terminal 
2. Create a separate namespace for development purposes by using the command ```kubectl create namespace development``` 
3. Use ```kubectl apply -f https://raw.githubusercontent.com/S-A-RB05/.github/main/deployment/ATM-deployment.yaml``` to roll out the necessary yaml files for minikube to run the application 
4. Run the ```minikube tunnel``` command to expose the services to your local machine 
5. Wait a minute or until deployed 
6. Go to http://localhost and you just deployed the ATM application 

 

 

## Troubleshoot 

In case of a minikube tunnel already running use the following steps for Linux/MacOS: 
1. Execute command: ```ps aux | grep minikube-tunnel``` 
2. Use the command ```sudo kill <PID>``` to kill the task with the corresponding id (replace <PID> with id
3. If that didn’t fix it, then try the following: 
4. ```minikube stop``` 
5. ```minikube delete --all --purge``` 
6. ```ps aux | grep minikube``` 
7. ```sudo kill <PID>``` all the tasks 
8. Try ```minikube tunnel``` again 
