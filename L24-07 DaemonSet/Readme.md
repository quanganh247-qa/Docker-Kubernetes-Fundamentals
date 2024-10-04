# L24-07

Let's deploy a Busybox as a DaemonSet.

![image](https://github.com/user-attachments/assets/90a5d93e-98a7-405f-b304-fba66638f073)

![image](https://github.com/user-attachments/assets/436581a7-37c3-4698-8f81-a3cafd9b24f4)

The daemon workload ensures that an instance of a pod is running on each one of these nodes

![image](https://github.com/user-attachments/assets/57cf9391-02a0-45c0-944f-ee8fb9d2fd1a)

![image](https://github.com/user-attachments/assets/87fc0942-4fa1-445d-b5ec-9c8f54bb59d8)

## Create the Deployment

    kubectl apply -f daemonset.yaml
    
![image](https://github.com/user-attachments/assets/fd6d9f2f-d6cb-4937-8cad-301b1b0de223)

     -> kubectl apply -f daemonset.yaml --validate=false

## Get the pods list

There should be one for each worker node.

    kubectl get pods --selector=app=daemonset-example -o wide

## Cleanup

    kubectl delete -f daemonset.yaml
