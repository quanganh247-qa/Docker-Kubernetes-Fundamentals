# L27-03

# Storage - the static way

![image](https://github.com/user-attachments/assets/ba89b8e7-0830-4d5a-bf01-39749e0bc8c7)

![image](https://github.com/user-attachments/assets/b38f9472-adae-4e0a-b58b-e1673e45836f)

![image](https://github.com/user-attachments/assets/8b31fd6e-7499-4cd1-a0d7-1a7c748a80e9)

![image](https://github.com/user-attachments/assets/99e26738-7523-4ff2-9612-04caa078b271)

![image](https://github.com/user-attachments/assets/3a8e9cf9-aa1b-404f-993f-3adb6acdd9d2)

![image](https://github.com/user-attachments/assets/2fcd044f-8f31-4e01-a566-5926632e3603)

![image](https://github.com/user-attachments/assets/f4cc9074-1e6a-44a5-8dda-38429c11fb6d)

![image](https://github.com/user-attachments/assets/4d2d9b73-46f3-4863-b801-99ade606b861)

![image](https://github.com/user-attachments/assets/8e3e4aba-2133-4377-9664-9558eb7bf0bf)

![image](https://github.com/user-attachments/assets/25a3cd46-57c1-43db-91f5-fa163b723141)

# Storage - the dynamic way

![image](https://github.com/user-attachments/assets/43c05e20-4580-4cda-80f0-afd312c10bb0)

![image](https://github.com/user-attachments/assets/e2e02581-5b23-457f-8391-74e862392a77)

![image](https://github.com/user-attachments/assets/1fedcd2a-05e7-4906-a0ab-41c2f72988e8)

![image](https://github.com/user-attachments/assets/2232529b-7676-4f27-ab5c-243a175f322b)

![image](https://github.com/user-attachments/assets/be27e6dd-ebbd-490f-8c0c-701e42026a11)

# Comparision

![image](https://github.com/user-attachments/assets/f9cadec6-b5aa-4a5a-b6b8-8b27ed37c0c6)


## Create the Persistent Volume

    kubectl apply -f pv.yaml

## Look at the pv

    kubectl get pv

## Deploy the claim

    kubectl apply -f pvc.yaml

## Look at the pvc

    kubectl get pvc

## Deploy the pod

    kubectl apply -f pod.yaml

## Connect to the Busybox instance

    kubectl exec mybox -it -- /bin/sh

## Create a file

    cd demo
    cat > hello.txt
    Hello World
    Enter and Ctrl-D
    ls
    exit

## Delete the pod

Let's delete the pod and deploy it again to validate that the file persisted.

    kubectl delete -f pod.yaml --force --grace-period=0

## Deploy the pod again

    kubectl apply -f pod.yaml

## Connect to the Busybox instance

    kubectl exec mybox -it -- /bin/sh
    cd demo
    ls
    cat hello.txt
    exit

## Cleanup

    kubectl delete -f pod.yaml  --force --grace-period=0
    kubectl delete -f pvc.yaml
    kubectl delete -f pv.yaml
