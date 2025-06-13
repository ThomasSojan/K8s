## Scheduling commands

### Taint and Tolerations

Taints and tolerations are only meant to restrict nodes from accepting certain pods.Taints and tolerations does not tell a pod to go to particular node, instead it tell node to only accept pods with certain tolerations.  

#### Taint- Node

Syntax

`kubectl taint nodes node-name key=value:taint-effect`

Taint effect can be `NoSchedule/PreferNoSchedule/NoExecute`

Example

`kubectl taint nodes node1 app=blue:NoSchedule`

#### Tolerations- PODs

![tolerations](images/tolerations.png)

