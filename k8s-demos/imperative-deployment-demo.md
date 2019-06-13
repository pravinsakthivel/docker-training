## Imperative Deployment (ie. deployment using CLI)

### Create a new deployment "web1" which contains one "ReplicaSet" 
### ReplicaSet contains "Pods"
### "Pods" contains Containers
```
$ kubectl create deployment web1 --image=nginx:1.7.9   
```

> Check the deployments 

    $ kubectl get deployments


> Check the replicasets

    $ kubectl get replicasets
    

> check the Pods

    $ kubectl get Pods


> check the Containers

    $ docker ps 


> Set the EDITOR tobe used (Optional if you want to VI)

    $ set KUBE_EDITOR=notepad

> Call edit for deployment

    $ kubectl edit deployments web1

> In newly opened notepad, locate 
    `replicas: 1`
  And replace with
    `replicas: 3`

> Save and Close

> Check the status of pods

    $ kubectl get pods --watch
