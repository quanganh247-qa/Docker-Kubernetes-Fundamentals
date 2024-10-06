# L28-02

![image](https://github.com/user-attachments/assets/7a7eae15-5e0e-422a-9737-1fc9ef93dc97)

![image](https://github.com/user-attachments/assets/55de5b25-7b51-4336-a22a-5317c1ea1813)

![image](https://github.com/user-attachments/assets/89961d85-aa43-488a-8c2a-99bfe9543feb)

![image](https://github.com/user-attachments/assets/50a5c010-4ca7-4e7c-8e54-a0e9381efd57)

![image](https://github.com/user-attachments/assets/152452b1-27cf-4bc7-adac-4ef66bff3c0c)

## Create the ConfigMap

    kubectl apply -f cm.yaml

## Get the ConfigMap info

    kubectl get cm
    kubectl describe configmap cm-example

Let's output the same information in YAML format

    kubectl get configmap cm-example -o YAML

## Deploy the pod

    kubectl apply -f pod.yaml

## Connect to the Busybox

    kubectl exec mybox -it -- /bin/sh

## Display the CITY env variable

    echo $CITY
    exit

## Cleanup

    kubectl delete -f cm.yaml
    kubectl delete -f pod.yaml --grace-period=0 --force
