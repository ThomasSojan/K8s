# Application Lifecycle Management

## Deployment Stratagies

- Recreate : Kill old pods, then start new pods. It has downtime.
- Rollout : It is the default strategy. It gradually replace old pods with new ones.  It has Zero downtime.

## Rolling Updates and Rolebacks

To apply changes in deployments

`kubectl apply -f deployment-def.yaml`

To make change in image version

`kubectl set image deployment/my-app-deployment <container>=<new-image>`

To check rollout status

`kubectl rollout status deployment/my-app-deployment`

`kubectl rollout history deployment/my-app-deployment`

To rollback new change

`kubectl rollout undo deployment/my-app-deployment`

## Commands and Arguments

![command-args](images/cmd-arg.png)

## ENV in K8s

![env-pod](images/env.png)

## Configmap in K8s

### Create configmap

Imperative

![configmap-imparative](images/configmap-imparative.png)

Declarative

![configmap-declarative.png](images/configmap-declarative.png)

### Inject configmaps to Pods
![configmap-pod](images/configmap-pod.png)
![configmap-pod](images/configmap-injection.png)

## Secrets in K8s

### Create Secretes

Imperative

![secret-imperative](images/secret-imperative.png)

Declerative

![secret-declerative](images/secret-declerative.png)

### Encode secrets

![secret-encode](images/secret-encode.png)

### Inject secrets to Pods
![secret-pod](images/secret-pod.png)

![secret-injection](images/secret-injection.png)

![secret-vol](images/secret-vol.png)

## Multi Container Pods

## Init Containers

## Self healing

## HPA

## VPA

## In place resize of Pods

![pod resizing without restart](images/In-place-pod-resize.png)








