# Kubernetes
Originally created by google, but now open source.

Can be deployed on all major clouds, and computers

kubernetes is container based, and standard images for many applications exist

When you have many containers on many nodes, you need to manage that. This management is called orchestration, and thats what kubernetes can do

### Pods
the smallest concept is the pod

a pod is a set of containers

containers in a pod are guarenteed to run alongside 

however, a pod is ephemeral. If it terminates, its gone forever. It exists temporarily. To recover information you need controllers, that can help restart. Controllers can also run several pods

The most popular controller is deployment. Deployment is persistent. Deployment launches the pod, and if it dies it automatically makes a new opne

another controller is the job controller. An abstraction of batch jobs. Can retry the job up to N times. handles pod and container failure. Facilitates parallel execution

a few other controllers:
* statfuleset- adds name and storage predictability
* CronJob- peridoically runs a pod

## Configuration Management
several methods to inject info into pods. There are 3 different 

you can also have external storage to save from ephemerali8ty

kubernetes provides the necessary hooks at pod launch time

when you launch a pod each container has its own IP to move data around

you can have services for load balancing

you can set traffic policies between these

### Pod scheduling
Kubernetes comes with an ok scheduler. It will organize based on computer specs

process:
* nodes tell what is available for the pods to use
* Pods say what they require, may be also cordoned off in a set of nodes
* a pod will start on a node only if a match can be made

it also has a prioritization

### users and permissions
Kubernetes have several kinds of "users", mostly for accessing the API, not owning resources. Permissions are set as part of the namespace concept or can be cluster wide. Once you get a user authroized to use the namespace, any user that can use that namespace has permissions

There are little restrictions from inside

### service accounts and programmatic access
User accounts are for humans

service accounts are for processes which run in pods

user accounts are intended to be global and unique

## Driving kubernetes
most interactions with kubernetes will involve YAML documents

this is for configuration

YAML is easy to use

## kubectl
kubectl create -f (filename) -Create new object
kubectl get (type) -n (namespace) -Query existing objects
kubectl edit (type) -n (namespace) (id) -Edit existing object
kubectl delete -f (filename) -Delete existing object
kubectl apply -f (filename) -Create or update an object

