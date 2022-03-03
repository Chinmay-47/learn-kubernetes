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
