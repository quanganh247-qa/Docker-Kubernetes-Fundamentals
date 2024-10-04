# L24-05

Let's now use the Deployment template instead of the Pod template.

![image](https://github.com/user-attachments/assets/ad6fb3b9-fc32-430e-a8d0-b8282098bd4f)

![image](https://github.com/user-attachments/assets/3df220d1-69d6-46ed-a573-85f4076b5eca)

![image](https://github.com/user-attachments/assets/7867d36a-91b1-4f08-8e64-ade0f7ac0a2c)

![image](https://github.com/user-attachments/assets/9a5611c6-b2a8-4fd6-951a-0e7c89f11398)

![image](https://github.com/user-attachments/assets/5493a01b-9898-40cf-bd08-14ce4df669a4)


## Create the Deployment

    kubectl apply -f deploy-example.yaml

## Get the pods list

    kubectl get pods -o wide
    
## Describe the pod

    kubectl describe pod deploy-example

## Get the Deployment info

    kubectl get deploy
    kubectl describe deploy deploy-example

## Get the ReplicaSet name

    kubectl get rs

## Describe the ReplicaSet

    kubectl describe rs

## Cleanup

    kubectl delete -f deploy-example.yaml
