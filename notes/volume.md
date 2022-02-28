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
