# L24-13

Let's now use the CronJob template.

![image](https://github.com/user-attachments/assets/29514cc1-c66a-4b51-aeef-88baf16312e5)

![image](https://github.com/user-attachments/assets/66b15a9b-b14f-4ee5-8912-792dea22d9b0)

![image](https://github.com/user-attachments/assets/3519cbdc-7321-4287-89af-9b0778c7010a)


## Create the Job

    kubectl apply -f cronjob.yaml

## Get the jobs list

    kubectl get cronjobs

## Get more info

    kubectl describe cronjob

## Get the pod name

Get the pod's log.  Something starting with **hello-**

    kubectl get pods

## Get the jobs list

Get the container's log.  You should see **Hello from the Job**.

    kubectl logs <podName>

## Cleanup

    kubectl delete -f cronjob.yaml
