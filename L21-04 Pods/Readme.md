# L21-04

Let’s first create a node running Nginx by using the imperative way.

## Pods architecture
![image](https://github.com/user-attachments/assets/2b2b84b4-8240-4887-9805-bfdd1397ce20)

## Pod creation
![image](https://github.com/user-attachments/assets/9428b944-1b45-4256-a80b-fbe27d0c0cfe)

## Pod deletion
![image](https://github.com/user-attachments/assets/bfd4c9fc-688d-4f56-8359-925c0eb44038)

## YAML 
![image](https://github.com/user-attachments/assets/ebea79bf-8bda-420c-9579-38e440371815)
![image](https://github.com/user-attachments/assets/b83c61c3-b253-42ba-890a-6e869c83cc2f)
![image](https://github.com/user-attachments/assets/82778a0e-dcb8-485b-9412-f653aba12857)

## kubectl - Pod cheatsheet
![image](https://github.com/user-attachments/assets/d0df7516-75ec-40e1-aca9-fc0906d37ddb)

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

