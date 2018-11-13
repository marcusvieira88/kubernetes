Introduction

This project is for staudies about Docker-Compose and Kubernets.

Below some commands used for create the images:

docker build -t "marcus88/node" . 
  -t = tag , name of image
  . = docs in root

docker exec -it marcus88/node
  -it = interactive mode, used for access the image and execute commands

docker-compose up -d 
    up = create all the services in the docker compose file
    -d = run detached(background)

MINICUBE - Create a virtualized environment 

minicube start

kubectl create -f web-application-pod.yaml  //creates the pod

kubectl create -f deployment.yaml  // creates the deployment environment, that manages the pods status

kubectl create -f service-web-application.yaml  // creates the service, that expose the web port and load balance the requests

kubectl create -f db-pod.yaml  // creates the db pod

kubectl create -f statefulset.yaml // creates the statefulset environment, that manages the volume and pods status

kubectl create -f service-db.yaml  // creates the service, that manages the pods requests

kubectl create -f volume-db-permissions.yaml // manages the permissions to write and read in the db volume (machine not in container)

kubectl get pods // shows all pods 

kubectl service service-web-application -- url // gets the service URL for access the application

kubectl delete pods web-application-pod-0 // deletes the pod

kubectl exec -it statefulset-mysql-0 sh // access the command line of pod

kubectl scale deplyment application-deployment --replicas=3 // scales the web pods

