### Kubernetes YAML File Example

##### Deploy a simple application on Kubernetes Cluster

- we will be deploying the “Hello World” equivalent application on Kubernetes Cluster.

- First we need to Install and Set Up** kubectl** on Linux: 
check this link  [https://kubernetes.io/docs/tasks/tools/install-kubectl-linux/](https://kubernetes.io/docs/tasks/tools/install-kubectl-linux/)

- Then open, “Terminal” and check Command Line Interface is working correctly.
```c
# Check Kubernetes and Docker CLI
$ kubectl version
$ docker version
```
- Use the kubectl create command to create a Deployment that manages a Pod. The Pod runs a Container based on the provided Docker image.
 - #### kubectl create -f hello-world.yaml

- View the Deployment:
```c
kubectl get deployments
```
- The output is similar to:
```c
NAME         READY      UP-TO-DATE   		AVAILABLE   		AGE
hello-world   1/1     	  1            			1           	4s 
```


- View the Pod:
```c
kubectl get pods
```
- The output is similar to:
```c
NAME    					   READY     STATUS    RESTARTS   	AGE
hello-world-8666cf6ccf-br9b5   1/1       Running      0          4s
```