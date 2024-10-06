# L28-04

![image](https://github.com/user-attachments/assets/e6bae740-be26-40af-b2c9-21f72635d105)

![image](https://github.com/user-attachments/assets/03e78dfd-541b-4002-ae1f-244beea57d9e)

![image](https://github.com/user-attachments/assets/e24df123-eb4c-4fc1-97ee-188049c51650)

![image](https://github.com/user-attachments/assets/53d53dc2-f672-4181-9047-3a2a88d73838)

To quickly encode/decode strings into base64

    https://www.base64encode.org/
    https://www.base64decode.org/

or on Windows, install base64

    choco install base64

on Linux/Mac

    echo [string] | base64
    echo [encodedString] | base64 -d

## Create the Secrets

    kubectl apply -f secrets.yaml

## Look at the secrets

    kubectl get secret
    kubectl describe secret secrets
    kubectl get secret secrets -o YAML

## Deploy the pod

    kubectl apply -f pod.yaml

## Connect to the Busybox

    kubectl exec mybox -it -- /bin/sh

## Display the USERNAME and PASSWORD env variables

    echo $USERNAME
    echo $PASSWORD
    exit

## Cleanup

    kubectl delete -f secrets.yaml
    kubectl delete -f pod.yaml --force --grace-period=0
