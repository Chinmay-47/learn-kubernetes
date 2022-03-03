# Kubernetes Notes

Notes for all topics in order of progression.

<br>
<hr>
<br>

### About Kubernetes

<br>

#### Introduction

- Kubernetes is an open source container orchestration tool
- It was developed by Google
- It helps manage containerized applications in various differing development environments
- These environments could be on the cloud, physical or a hybrid of the two

<br>
<hr>
<br>

#### Need for a container orchestration tool

- There is a trend of applications moving to microservice based architectures from monolith based architectures
- This has resulted in an increased usage of containers
- Manging these containers/services across environments using custom scripts or self made libraries 
can be extremely difficult
- Hence, using a container orchestration tool is useful

<br>
<hr>
<br>

#### Features offered by container orchestration tools

- They can provide high availability with little/no downtime
- This is important for applications that need to be up all the time
- They also provide scalability with high performance
- This makes the applications flexible to increasing or decreasing loads
- They also provide backups to restore as disaster recovery mechanisms

<br>
<hr>
<br>

### Kubernetes Architecture

<br>

The Kubernetes architecture is made up of:

- At least one master Node (physical or virtual)
- Connected to it are multiple worker nodes
- There is also a virtual network for the nodes to communicate with each other

<br>
<hr>
<br>

#### Worker Nodes
- Worker nodes each have a "kubelet" process running on them
- kubelets are Kubernetes processes that allow for the cluster of nodes to communicate with each other 
and to run applications
- Each worker node has containers of different applications deployed on it
- Depending on workload distribution, nodes may have differing number of running containers

<br>
<hr>
<br>

#### Master Node
- Master node runs Kubernetes processes required to run and manage the cluster
- The master node runs the API server, which is essentially the entry point to the cluster
- The master node also runs the Controller manager process 
which essentially keeps track of what's happening in the cluster
- The master node also runs a scheduler, responsible for scheduling containers on the worker nodes 
based on workload and available server resources on each node
- The master node also has an etcd key value storage, to hold the current state of the cluster and configurations
- The backups and restorations are achieved from this etcd storage

<br>
<hr>
<br>

<img src="https://k8s.picocourses.com/assets/course/arch/k8s-architecture.png">

<br>
<hr>
<br>

### Node and Pod

<br>

We know that a Node is a physical or virtual machine

<br>
<hr>
<br>

#### Pod

- A Pod is the smallest unit in Kubernetes
- It is an abstraction over a container
- We usually run 1 application per pod
- Each pod gets its own IP address
- They are internal IP addresses that the pods use to communicate with each other
- Pods in Kubernetes are ephemeral (pods can die) but are re-created
- A new IP address is assigned on re-creation of the pod

<br>
<hr>
<br>

<img src="https://matthewpalmer.net/kubernetes-app-developer/articles/networking-overview.png">

<br>
<hr>
<br>

### Service and Ingress

<br>
<hr>
<br>

#### Service

- Service is a static IP address assigned to the Pods
- The lifecycle of the service and pod are not connected
- Hence, the IP address will persist even on Pod re-creation
- Services can be internal or external 
(For example, we would want the database service to be internal but the app service to be external)
- The type can be specified on creation of the service
- The default type of a service is Internal
- However, an external service is not practical to expose for production
- The external service usually has the Node IP address and the port on which the service is exposed

<br>
<hr>
<br>

#### Ingress

- We use the Ingress in production settings
- Instead of requests going directly to a service, they go to the Ingress
- The requests are received by the Ingress and forwarded to the service

<br>
<hr>
<br>

<img src="https://miro.medium.com/max/1400/1*ebSKyCjwsBMM1CLHqpK_bg.jpeg">

<br>
<hr>
<br>

### ConfigMap and Secret

<br>
<hr>
<br>

#### ConfigMap

- ConfigMap contains external configurations of the application
- It usually contains configuration details like URLs of databases 
and other services used in the application
- In Kubernetes you connect the services to the URLs/endpoints in the ConfigMap

<br>
<hr>
<br>

#### Secret

- Some configuration details may be credentials and other sensitive information
- Placing such details in the ConfigMap would be insecure
- Secret is like ConfigMap but can be used to store sensitive details
- It is base64 encoded by default but encryption using third party tools are recommended

<br>
<hr>
<br>

### Volume

<br>

- There is often data being generated and written by apps and their databases
- Since they are in pods, any restart of the pods would result in data loss
- To prevent this we can use Volume in Kubernetes
- It is a way of attaching physical memory to the pods
- This memory storage could either be on the local machine or it could be remote, 
outside the cluster entirely (like cloud storage)
- Hence, we can persist memory from the Kubernetes components
- However, an important point to remember is that Kubernetes does not manage data persistence
- We, as users/administrators are responsible for backing up data, replicating it and managing its storage

<br>
<hr>
<br>

<img src="https://res.cloudinary.com/practicaldev/image/fetch/s--0dxCxZHZ--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://learncloudnative.com/static/bd77805968e552ae0f670fc6b1800bd4/914ae/volumes-1.png">

<br>
<hr>
<br>

### Deployment and StatefulSet

<br>
<hr>
<br>

#### Deployment

- Deployment is basically a blueprint for application pods 
- In Kubernetes users/administrators do not directly work with or create pods, instead we create deployments
- In Deployments we can specify the number of replicas for a given pod to scale up or down
- While pods are abstractions over containers, deployments are abstractions over pods
- A disadvantage of deployments is that we cannot use them to replicate pods like databases that maintain a state

<br>
<hr>
<br>

#### StatefulSet

- StatefulSet allows us to replicate pods that maintain state
- They also ensure data consistency and synchronization
- However, deploying database applications using StatefulSets in Kubernetes can often be tedious
- Hence, it is a common practice to host databases outside the Kubernetes clusters

<br>
<hr>
<br>

### Kubernetes Configuration


- In Kubernetes UI, API and CLI clients all have to talk to the API Server 
which is the main and only entry point into the cluster.
- All these request have to be in YAML or JSON format
- The configuration requests in Kubernetes are declarative in nature

<br>
<hr>
<br>

The K8 configuration files in Kubernetes have 3 main parts

#### Metadata

- The initial part of the configuration files for deployments and services usually contain the metadata
- In this section metadata like the name of the component itself are declared

#### Specification

- The next part of the configuration files have specifications
- This is where we can declare specific configuration settings like the number of replicas 
and the required ports to be exposed
- These attributes of "spec" are specific to the kind of configuration file

#### Status

- We do need to declare this part of the configuration file
- It is automatically generated and added by Kubernetes
- This is what is used by the controller manager to check if the desired state == actual state
- This status information comes from the etcd storage in Kubernetes

<br>
<hr>
<br>

<img src="https://i1.wp.com/www.upnxtblog.com/wp-content/uploads/2017/11/azure12.png?resize=619%2C456">

<br>
<hr>
<br>
