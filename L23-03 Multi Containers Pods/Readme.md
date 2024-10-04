# L23-03

Let’s create multiple containers in a Pod using a YAML file.  We'll use the Busybox container to get the default page served by the Nginx container.
![image](https://github.com/user-attachments/assets/b4505c89-b5c9-42d9-af83-eefe58b9e6fd)
  ![image](https://github.com/user-attachments/assets/b1ea5988-c7fd-4e6b-bde4-7abdc94d4395)

## Pod networking
![image](https://github.com/user-attachments/assets/7710437e-d8d9-4399-bc9c-854c913eb561)

![image](https://github.com/user-attachments/assets/53637035-9b89-4d78-a842-dc5d678fc8ba)

## Create the pod

    kubectl create -f two-containers.yaml

## Get some info

    kubectl get pods -o wide
    kubectl describe pod two-containers

## Connect to the BusyBox container

    kubectl exec -it two-containers --container mybox -- /bin/sh

## Fetch the HTML page served by the Nginx container

This will output the content of the Web page in the terminal.

    wget -qO- localhost

## Quit

    exit

## Cleanup

    kubectl delete -f two-containers.yaml --force --grace-period=0
