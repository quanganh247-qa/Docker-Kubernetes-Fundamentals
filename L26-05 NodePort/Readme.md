# L26-05

Let's expose a deployment using a Nodeport service.

![image](https://github.com/user-attachments/assets/f6a2f8db-5fbc-4fba-b747-c0586b252c47)

- NodePort mở rộng dịch vụ ClusterIP:
    NodePort cho phép truy cập dịch vụ từ bên ngoài cluster, bổ sung tính năng cho ClusterIP.
- Tính khả dụng (Visibility):
    NodePort cung cấp khả năng truy cập cả từ bên trong và bên ngoài cluster, làm cho dịch vụ dễ dàng tiếp cận hơn.
- NodePort:
    Đây là cổng mà dịch vụ sẽ lắng nghe từ bên ngoài. Cổng này có thể được định nghĩa tĩnh hoặc động, trong khoảng từ 30000 đến 32767.
    Khi một yêu cầu được gửi đến cổng NodePort trên bất kỳ node nào trong cluster, yêu cầu đó sẽ được chuyển tiếp đến Service tương ứng.
- Cổng (Port):
    Đây là cổng mà Service đang lắng nghe bên trong cluster và được chỉ định cho các Pods.
- TargetPort:
    TargetPort là cổng mà các Pods đang lắng nghe. Service sẽ chuyển tiếp yêu cầu đến         TargetPort của Pods, giống như trong ClusterIP.

![image](https://github.com/user-attachments/assets/d7af23cb-e0db-40fb-a85d-caa90e924c57)

![image](https://github.com/user-attachments/assets/ab23396f-0593-4cea-b8c8-bb9de775f95d)


## Deploy the app

    kubectl apply -f deploy-app.yaml

## Deploy the NodePort service

    kubectl apply -f nodeport.yaml

## Get the pods list

    kubectl get pods -o wide

## Use the nodeport

Since we are using Docker Desktop and that the Docker Desktop node is mapped to localhost, to reach the service you need to use **localhost** + the **nodeport**.

When using a Cloud provider, you would need to get a node IP address instead of localhost.

Get the node public IP address

    kubectl get nodes -o wide

## Cleanup

    kubectl delete -f nodeport.yaml
    kubectl delete -f deploy-app.yaml
