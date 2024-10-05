# L26-03

![image](https://github.com/user-attachments/assets/0deafbb1-6dec-4b63-ab18-aba4703d86f2)

- Service là một đối tượng trong Kubernetes giúp định nghĩa cách mà các ứng dụng có thể giao tiếp với nhau. Nó cung cấp một điểm truy cập ổn định cho các Pods.
- Pod IP không đáng tin cậy:
    Các địa chỉ IP của Pods có thể thay đổi khi chúng được khởi động lại hoặc thay thế, vì vậy không thể dựa vào chúng để giao tiếp liên tục.
- Service IP là bền vững:
    Ngược lại với Pods, địa chỉ IP của Service là cố định, giúp đảm bảo rằng các ứng dụng có thể giao tiếp với nhau mà không bị ảnh hưởng bởi sự thay đổi trong cấu hình của Pods.
- Địa chỉ IP tĩnh và tên DNS tĩnh:
    Service có một địa chỉ IP tĩnh mà không thay đổi, và nó cũng có thể có một tên DNS tĩnh.
- Cú pháp tên DNS thường là:

       [tên_service].[namespace].svc.cluster.local
       
Điều này cho phép các ứng dụng trong cùng một namespace hoặc namespace khác dễ dàng tìm và giao tiếp với Service.
- Service là cách truy cập vào Pods:
    Services cung cấp một cách để truy cập và giao tiếp với các Pods, bất kể số lượng và trạng thái của chúng, giúp duy trì tính sẵn sàng và ổn định cho ứng dụng.
  
## Deploy the service

    kubectl apply -f clusterip.yaml

## Deploy the app

    kubectl apply -f deploy-app.yaml

## Deploy Busybox

    kubectl apply -f pod.yaml

## Get the pods list

    kubectl get pods -o wide

## Connect to the BusyBox container

    kubectl exec mybox -it -- /bin/sh

## Get the Nginx home page thru the ClusterIP service

    wget -qO- http://svc-example:8080
    exit

## Cleanup

    kubectl delete -f clusterip.yaml
    kubectl delete -f deploy-app.yaml
    kubectl delete -f pod.yaml --grace-period=0 --force
