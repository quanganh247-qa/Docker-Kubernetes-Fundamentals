# L25-02

**NOTE: If you are running this lab on a ARM64 laptop/PC, edit the YAML file and change the image name from "hello-app" to "hello-arm" keeping the tag name as is.**

![image](https://github.com/user-attachments/assets/bf94c6d8-860c-4c11-bb89-80c676b6b52b)

- maxSurge:
    Đây là số lượng tối đa các Pods mới có thể được tạo ra trong quá trình cập nhật.
    Giá trị này có thể được xác định bằng một số cụ thể hoặc một tỷ lệ phần trăm so với tổng số Pods hiện có.
    Ví dụ: Nếu bạn có 10 Pods và maxSurge là 25%, bạn có thể tạo thêm tối đa 2 Pods mới trong quá trình cập nhật.

- maxUnavailable:
    Đây là số lượng tối đa các Pods có thể không khả dụng (unavailable) trong quá trình cập nhật.
    Điều này đảm bảo rằng một số lượng tối thiểu Pods vẫn hoạt động trong khi cập nhật diễn ra.
    Ví dụ: Nếu bạn có 10 Pods và maxUnavailable là 25%, tối đa 2 Pods có thể không khả dụng trong quá trình cập nhật.


## Create a V1 Deployment

    kubectl create -f hello-deployment.yaml

## Get the deployment status

    kubectl rollout status deployment/hello-dep

## Get the pods list

    kubectl get pods -o wide

## Describe the pod

    kubectl describe pod hello-dep

## How many ReplicaSets do we have?

    kubectl get rs

Do not delete the Deployment yet!

---

## Create a V2 Deployment

Edit the YAML file and change the container version from 1.0 to 2.0. Save the file.
 
## Create the Deployment

    kubectl apply -f hello-deployment.yaml

## Get the deployment status

    kubectl rollout status deployment/hello-dep

## Get the pods list

    kubectl get pods -o wide

## How many ReplicaSets do we have?

    kubectl get rs

## Get the deployment history

    kubectl rollout status deployment/hello-dep

---
 
## Rollback

## Undo the last deployment using either

    kubectl rollout undo deployment/hello-dep

or

    kubectl rollout undo deployment/hello-dep --to-revision 1

## Get the deployment history

    kubectl rollout status deployment/hello-dep

## How many ReplicaSets do we have?

    kubectl get rs

## Cleanup

    kubectl delete -f hello-deployment.yaml
