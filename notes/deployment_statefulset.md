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
