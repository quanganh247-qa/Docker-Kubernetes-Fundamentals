# L24-03

Let's now use the ReplicaSet template instead of the Pod template.

![image](https://github.com/user-attachments/assets/5c341517-416c-49b5-bbf0-c80a9f98fb18)

![image](https://github.com/user-attachments/assets/7d10144e-402a-44a2-bdb2-9f090de5d73e)


## Create the ReplicaSet

    kubectl apply -f rs-example.yaml

## Get the pods list

    kubectl get pods -o wide

## Get the ReplicaSet name

    kubectl get rs

## Describe the ReplicaSet

    kubectl describe rs rs-example

## Cleanup

    kubectl delete -f rs-example.yaml
