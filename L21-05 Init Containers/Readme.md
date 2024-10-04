# L21-06

Let's use an Init container.

![image](https://github.com/user-attachments/assets/e018f6de-d1ef-4543-ad8e-9c55660dfac9)

![image](https://github.com/user-attachments/assets/e3d86ae2-763a-488d-87e9-2a5a1e206462)
![image](https://github.com/user-attachments/assets/b0e7c82d-04a2-46d8-8724-f4ed8f2c8232)
![image](https://github.com/user-attachments/assets/e6efb6a5-bc7b-4fd5-a84c-44489e9ecc23)

## Create the deployment


    kubectl apply -f myapp.yaml

Wait for the main pod to come up

    kubectl get pods

## Connect to the Nginx container

    kubectl exec -it init-demo -- /bin/bash

## Hit the default webpage

It should be the one downloaded by the Init container from http://info.cern.ch

    curl localhost
    exit

## Cleanup

    kubectl delete -f myapp.yaml
