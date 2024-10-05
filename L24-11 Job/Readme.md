# L24-11

Let's now use the Job template.

![image](https://github.com/user-attachments/assets/87325995-99db-438d-aa8a-158afd8c54c7)

![image](https://github.com/user-attachments/assets/7f8a655f-3a37-4c7a-9cf0-cba545ca4dde)

![image](https://github.com/user-attachments/assets/793c780c-e8a3-4e3c-a1c9-8e4c02124d31)

## Create the Job

    kubectl apply -f job.yaml

## Get the jobs list

    kubectl get jobs

## Get more info

    kubectl describe job

## Get the pod name

Get the pod's log.  Something starting with **hello-**

    kubectl get pods

## Get the jobs list

Get the container's log.  You should see **Hello from the Job**.

    kubectl logs <podName>

## Cleanup

    kubectl delete -f job.yaml
