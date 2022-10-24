### What is Kubernetes
Kubernetes is an open-source orchestration tool developed by google for automating deployment, scaling, and managing containerized applications.



 ### Why do we need Kubernetes?
- Let’s say you have a couple of java applications. You can package it into a container and run it on a server containing docker. For this scenario, there is no complexity.

- You package your application into a Docker image using Dockerfile and expose a port on a host for the external world to access it.

- The only downside is that it is a single point of failure as it is a single server. So you need an efficient mechanism to handle a single point of failure.

- This is why you need a container clustering & orchestration tool like Kubernetes to scale applications on-demand and withstand single node failures.

### What features Does  Kubernetes Offer?
- Assures high availability with zero downtime
- Highly performant and scalable
- Reliable infrastructure to support data recovery with ease

### Kubernetes Architecture:
- To understand how Kubernetes works, there are two related concepts you need to
understand. The first is the Kubernetes object model. Each thing Kubernetes manages is represented by an object, and you can view and change these objects’
attributes and state. The second is the principle of declarative management.
Kubernetes expects you to tell it what you want the state of the objects under its
management to be; it will work to bring that state into being and keep it there.



- ### Kubernetes Components:
Managed Kubernetes Cluster operates in master and worker architecture. In which Kubernetes Master gets all management tasks and dispatch to appropriate Kubernetes worker node based on given constraints.

- 1. **Master Node**
- 2. **Worker Node**

![](https://miro.medium.com/max/720/1*TQw_pFtFWJhoUjhN993o1Q.png)

 - ![](https://miro.medium.com/max/720/1*t2kujM8JnnAU1EmJkBX-QQ.png)

#### - The Master Components
- Let’s begin with the Master components, as you probably already guessed, they run in the Master node, and they are the control plane making global decisions inside the cluster.

- These components are the API server, etcd, scheduler, controller-manager, and cloud controller manager.
- **API server**: This component exposes via API the Kubernetes control plane. This is how the Kubernetes CLI or “kubectl” interacts with the cluster.

- **The etcd**: Etcd is a key/value store database where all the Kubernetes data gets stored and when all means like all of it.

- **The scheduler**: The scheduler watches for pods and finds them a node with enough resources to run.

- **Then, the controller manager**. This component is a single binary composed of four sub-processes and they are:

- **The node controlle**r: Responsible for the health of the nodes in the cluster.
- **The replication controller**: responsible for keeping the desired amount of pods for each replication.
- **The endpoints controller**: handles the Endpoints object that links services and pods.
- **The service account and token controller**: handles the default accounts and API access for namespaces.

### Worker Node Components
- These components are known for running on each worker node, unlike the master components, which mainly runs in one master at the time, the worker node has four very light components, make sense because you want to reserve most of the space for your pods.

- **The kubelet**, which makes sure all containers are running and healthy.

- **The proxy** allows communication to the inside network of the cluster by using network rules, mainly used for development and testing pods, it is recommended to remove it in production for security reasons.

- **The container runtime**, which is responsible for running the containers, the most common runtimes choices are: Docker and Containerd.

### Some Of The Key K8s components Are :
- **Pods**: Smallest unit of k8s, which is an abstraction of the container application
- **Services & Ingress**: To manage external communication between nodes and internal pod level communication
- ** ConfigMaps**: To manage the end-point URLs required by the pods/ DB’s
- **Secrets**: To keep app-level passwords and secret keys securely using based64 encoding
- **Volume**: For Persistent data storage
- **Deployments**: To deploy create replicas & manage stateless apps
- **Statefulsets**: For stateful apps and databases
