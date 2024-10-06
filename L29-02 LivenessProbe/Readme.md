# L29-02

![image](https://github.com/user-attachments/assets/1cff3475-346e-4e7c-9c8d-ca321766f696)

![image](https://github.com/user-attachments/assets/5857ab71-3f05-44e8-8a6f-4794e453f5ec)

![image](https://github.com/user-attachments/assets/2e5011c5-54fd-475f-add4-a2b26c273051)

![image](https://github.com/user-attachments/assets/c03240b0-7735-40a2-8196-2be56fa24674)

![image](https://github.com/user-attachments/assets/35349cc9-66f6-462e-8f61-ec68d25677a2)

![image](https://github.com/user-attachments/assets/55d47ae2-afc5-4e56-b7ba-f79a407344ee)

## Deploy the pod

    kubectl apply -f pod.yaml

## Look at the pod events

    kubectl describe pod liveness-example

## Cleanup

    kubectl delete -f pod.yaml --force --grace-period=0
