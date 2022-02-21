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

