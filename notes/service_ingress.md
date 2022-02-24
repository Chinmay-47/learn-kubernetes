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
