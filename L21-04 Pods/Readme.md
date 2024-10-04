# L21-04

Let’s first create a node running Nginx by using the imperative way.

## Pods architecture
![image](https://github.com/user-attachments/assets/2b2b84b4-8240-4887-9805-bfdd1397ce20)

## Pod creation
![image](https://github.com/user-attachments/assets/9428b944-1b45-4256-a80b-fbe27d0c0cfe)


## Create the pod

    kubectl run mynginx --image=nginx

## Get a list of running pods

    kubectl get pods

## Get more info

    kubectl get pods -o wide
    kubectl describe pod mynginx

## Delete the pod

    kubectl delete pod mynginx

## Create a pod running BusyBox

Let’s now create a node running BusyBox, this time attaching bash to our terminal.

    kubectl run mybox --image=busybox -it -- /bin/sh

## List the folders and use command

    ls
    echo -n 'A Secret' | base64
    exit

## Cleanup

    kubectl delete pod mybox

## Create a pod using the declarative way

Let’s now create a node using a YAML file.

    kubectl create -f myapp.yaml

## Get some info

    kubectl get pods -o wide
    kubectl describe pod myapp-pod

## Attach our terminal

    kubectl exec -it myapp-pod -- bash

Print the DBCON environment variable that was set in the YAML file.

    echo $DBCON

## Detach from the instance

    exit

## Cleanup

    kubectl delete -f myapp.yaml

