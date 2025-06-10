# Kubernetes

## Kubernetes Architecture

### 1.etcd
The etcd data store stores information regarding the k8s resources such as
- Nodes
- Pods
- Configs
- Secretes
- Accounts
- Roles
- Bindings
- Others

Every information you see from kubectl command is from etcd server. Every changes you made in the cluster are updated in the etcd.
### 2.kube-api server
The kube-api server is at the center of all the different task that needs to performed to make a change in the K8s cluster. The kube-api server is responsible for
- Authenticate User
- Validate Request
- Retrieve Data
- Update ETCD
- Scheduler
- Kubelet

To summarize it is responsible for authenticating and validating requests, retrieving and updating data in the etcd data store, kube-api server is the only component that interacts directly with the etcd data store.The other components such as scheduler, kube control manager and kubelet uses the API server to perform updates in the cluster in their respective areas.

### 3.kube control manager
Kube controller manager manages various controllers in K8s. A controller is a process that continuously monitors the state of various components within the system and work towards bringing the whole system to the desired state.
- Node controller is responsible for monitoring the state of nodes and take neccesary actions to keep the application running. 
- Replication controller is responsible managing the replica sets and ensuring that the desired number of pods are available at all times within the set.

There were many controllers are available in k8s all these controllers are managed by kube control manager.

### 4.kube scheduler
The kube scheduler decides which pod goes where. The scheduler looks at each pods and tries to find the best node for it. The scheduler goes through two phases to identify the best node for the pod. In the first phase the scheduler tries to filter out the nodes that do not have sufficient cpu and memory requested by the pod. In the second phase scheduler rank the nodes based on the available resources after placing the pod. The node with better rank will be selected for placing the pod. This can be customized and we can write our own scheduler.

### 5.kubelet
The kubelet in the k8s worker node regesters the node with k8s cluster. When it recieve instruction to load a pod on the node, it request the container runtime to pull the required image and run an instance. The kubelet then continues to monitor the state of the pod and containers in it and reports to the kube API server on a timely basis. 

### 6.kube proxy
The kube proxy is a process that runs on each node in the k8s cluster. Its job is to look for new servieces and when a new service is created, it create appropriate rules on each node to forward traffic to those services to the backend pods. 
