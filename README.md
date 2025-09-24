# learn-k8s
Repo for learning about container orchestration

What is Kubernetes?
 - manages containers

 Monolithic vs Microservice

- Monolithic architecture from the way I can understand is a whole application living on one codebase. If you have to make an update on a small feature you would have to rebuild and redeploy the entire application

- Microservice architecture is breaking down that entire application into smaller and much manageable way. so each feature is independent from one another and they would talk to one abother through api's

Features of orchestration tools

 - high availability
 - scalability
 - DR - backup and restore

 K8s Architecture

 1 Master Node (physical or vitual machine)

 Worker Nodes - which have a kubelet process(primary node agent) running on it - makes it possible for the cluster to talk to each other and execute task on the node - *This is where your applications are running

 So what is running on the Master Node?

1. API Server - Entry point to k8s cluster (ui, api, cli will talk to the api server)

2. Controller Manager - keeps track of whats happening on the cluster (whats need to be repaired or if a container crashed and needs to be restarted)

3. Scheduler - responsible for scheduling pods and decides which node new pods should be scheduled/placed

4. etcd - k8s backing store (takes snapshots)

Virtual Network
 basically creates one unified machine

 Main Kubernetes Components

 1. Pod 
    smallest unit in k8s
    Abstraction over container
    Usually 1 Application per pod
    Each Pod gets it own IP address
    can die very easily (epipheral)
    new ip address on re-creation

2.   Service  
    static IP Address
    lifecycle of pod and service are not connected (if pod dies service will stil be okay!)
    create external service to open application to the internet
    can create a type of service (internal or external)
    will default to internal

3. Ingress    
    if you want the application to have domain name - ingress will come into forward it to service

4. ConfigMap 
    ext configuration of the application (database urls etc)
    connect it to the pod so it gets the data of the configMap

5. Secret
    just like configMap but only used to store secret data and is encoded in base64 (database username, password etc)
    reference secrett in deployment/pod

6. Volume    
    attaches a physical storage to your pod