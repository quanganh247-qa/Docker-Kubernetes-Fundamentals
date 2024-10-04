# L24-07

Let's deploy a Busybox as a DaemonSet.

![image](https://github.com/user-attachments/assets/90a5d93e-98a7-405f-b304-fba66638f073)

![image](https://github.com/user-attachments/assets/436581a7-37c3-4698-8f81-a3cafd9b24f4)

The daemon workload ensures that an instance of a pod is running on each one of these nodes


## Create the Deployment

    kubectl apply -f daemonset.yaml

## Get the pods list

There should be one for each worker node.

    kubectl get pods --selector=app=daemonset-example -o wide

## Cleanup

    kubectl delete -f daemonset.yaml
