# Kubernetes Summary (K8s)

## Definition

Container orchestration tool / framework

- high availability
- scalability or high performance
- disaster recovery

* Kubectl : CLI to configure Kubernetes and manage apps
* Kubelet: Kubernetes agent running on nodes
* Node: Single Server in the kubernetes cluster
* Control Plane: set of containers that mange the cluster
- includes: API Server, scheduler, controller manager, etcd
- sometimes called master

## Kubernetes components:

### Pod:

- smallest unit of K8s
- abstraction over containers
- one app by Pod
- each Pod gets its own ip address

### Service:

- permanent IP address
- lifecycle of Pod and Service are not connected

### Ingress: convert the url to secure protocol and domain name

### ConfigMap:

- external configurations ( db config)

### Secret:

- store secret dat
- base64 encoded

### Volumes:

- storage on local machine
- or remote outside of the K8s cluster

## Deployment StatefullSet

## Minikube:

is a local Kubernetes

- minikube start
