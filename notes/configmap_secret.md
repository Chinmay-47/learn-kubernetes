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
