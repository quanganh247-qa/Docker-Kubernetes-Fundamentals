![image](https://github.com/user-attachments/assets/fa506146-a6d8-4fa2-a99a-153b2efeed43)

1. Pods
- Là đơn vị nhỏ nhất trong K8s
- Chứa một hoặc nhiều container
- Dùng khi: Cần chạy ứng dụng
- Cách dùng: Thường không tạo trực tiếp, mà thông qua Deployment/DaemonSet

2. ReplicaSets
- Đảm bảo số lượng pod replica chạy đúng theo cấu hình
- Dùng khi: Cần duy trì số lượng pod nhất định
- Cách dùng: Thường được tạo tự động bởi Deployment

3. Deployments 
- Quản lý việc triển khai và cập nhật ứng dụng
- Dùng khi: Triển khai ứng dụng stateless
- Cách dùng: Tạo qua file YAML, định nghĩa image, replicas,...

4. DaemonSets
- Đảm bảo mỗi node chạy một bản copy của pod
- Dùng khi: Chạy các agent như monitoring, logging trên mọi node
- Cách dùng: Tạo qua YAML file

5. Services
- Cung cấp network endpoint ổn định cho pods
- Dùng khi: Cần expose pods ra network
- Cách dùng: Định nghĩa selector để tìm pods cần expose

6. Namespaces
- Phân chia cluster thành nhiều virtual cluster
- Dùng khi: Cần tách biệt resources theo team/project
- Cách dùng: Tạo namespace và gán resources vào

7. Nodes
- Máy worker chạy các pods
- Là server vật lý hoặc VM trong cluster
- Dùng khi: Cần thêm computing resource
- Cách dùng: Thêm node vào cluster thông qua kubeadm
