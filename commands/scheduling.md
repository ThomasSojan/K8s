## Scheduling commands

### Taint- Node

Syntax

`kubectl taint nodes node-name key=value:taint-effect`

Taint effect can be `NoSchedule/PreferNoSchedule/NoExecute`

Example

`kubectl taint nodes node1 app=blue:NoSchedule`

## Tolerations- PODs

![tolerations](../images/tolerations.png)

