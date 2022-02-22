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
