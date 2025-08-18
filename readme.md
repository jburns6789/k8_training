Kubernetes:
K8 expects all images to be built and exported to docker hub
one config file per object we want to create
we have to manually setup all networking

Have to be very explicit with all of the networking setup

Get a simple container running on local k8 cluster:
image needs to be hosted on docker hub
make one config file to create the container
make one config file to setup the network

Configfile:
Used to create objects
example object types: stateful set, replicaController, Pod, Service
each api version defines a different set of objects we can use

Node -> Pod -> container -> software
containers in pods are tighly coupled and can't exist with out one another. ex postgres, logger, backup manager

Pod -> runs one or more closely realted containers
Services -> sets up networking in a Kubernetes Cluster

4 types of services: cluster IP, NodePort, LoadBalancer,Ingress

NodePort only good for dev purpose

Internet -> Kubernetes node VM -> kubeproxy connects to both <-> serviceNode(s) Port -> Pod -> port3000 -> multiclient container

docker desktop k8 configured
simplek8 % kubectl apply -f client-pod.yaml
simplek8 % kubectl apply -f client-node-port.yaml
simplek8 % kubectl get pods
simplek8 % kubectl get services

access locally: localhost31515 (nodePort) per docker desktop
