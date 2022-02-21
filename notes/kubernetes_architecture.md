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

