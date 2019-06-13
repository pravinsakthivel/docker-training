## Rolling Update to existing deployment

> Use KUBE_EDITOR to define text editor

    $ set KUBE_EDITOR=notepad

> Use kubectl to EDIT the deployment "web1"

    $ kubectl edit deployments web1

> Replace "nginx:1.7.9" to "nginx:1.8.0"
    Save and Close the file.

> Try following commands to check status

    $ kubectl get pods
    $ kubectl get deployments
    $ kubectl rollout status deployments web1

> Notice that, Update has actually FAILED. Lets UNDO

    $ kubectl rollout undo deployments web1

> Try getting deployment / pods

    $ kubectl get pods
    $ kubectl get deployments
    $ kubectl rollout status deployments web1
