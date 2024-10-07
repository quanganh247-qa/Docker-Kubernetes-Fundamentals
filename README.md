![image](https://github.com/user-attachments/assets/39f9e5e1-3006-4233-ad9f-c3d1d8667ff7)

![image](https://github.com/user-attachments/assets/458261b3-d925-4ab1-9f9f-201c976325cc)

1. Pods
- Là đơn vị nhỏ nhất trong K8s
- Chứa một hoặc nhiều container
- Dùng khi: Cần chạy ứng dụng
- Cách dùng: Thường không tạo trực tiếp, mà thông qua Deployment/DaemonSet

2. ReplicaSets
- Đảm bảo số lượng pod replica chạy đúng theo cấu hình
- Dùng khi: Cần duy trì số lượng pod nhất định
- Cách dùng: Thường được tạo tự động bởi Deployment

Deployments

Quản lý ReplicaSets và cung cấp declarative updates cho Pods
Dùng khi: Deploy ứng dụng stateless, cần rolling updates/rollbacks
Cách dùng: Define desired state trong manifest file
Ví dụ phổ biến: Web applications, microservices

StatefulSet

Quản lý Pods có state và unique identity
Dùng khi: Cần persistent storage và network identity ổn định
Cách dùng: Define trong manifest với PersistentVolumeClaims
Ví dụ phổ biến: Databases, message queues

DaemonSet

Đảm bảo mỗi node chạy một copy của pod
Dùng khi: Cần chạy pod trên tất cả (hoặc một số) nodes
Cách dùng: Define pod template áp dụng cho nodes
Ví dụ phổ biến: Monitoring agents, log collectors

Services

Expose pods với stable network endpoint
Dùng khi: Cần truy cập đến pods
Các loại:

ClusterIP: Internal access
NodePort: External access through node port
LoadBalancer: External access through cloud provider

Ví dụ phổ biến: API endpoints, web services

Namespaces

Phân chia tài nguyên cluster thành các không gian riêng biệt
Dùng khi: Cần isolation giữa teams, projects, environments
Cách dùng: Create namespace và assign resources
Ví dụ phổ biến: dev, staging, prod environments

Job/CronJob

Job: Tạo pods chạy task đến khi hoàn thành
CronJob: Job chạy theo lịch định sẵn
Dùng khi: Cần thực hiện batch processing hoặc scheduled tasks
Ví dụ phổ biến: Backup jobs, cleanup tasks

ConfigMaps

Lưu trữ configuration data non-sensitive
Dùng khi: Cần external configuration cho applications
Cách dùng: Mount như files hoặc environment variables
Ví dụ phổ biến: Application settings, URLs

Secrets

Lưu trữ sensitive data
Dùng khi: Cần bảo mật thông tin như passwords, tokens
Cách dùng: Mount như files hoặc environment variables
Ví dụ phổ biến: Database credentials, API keys

Volumes

Cung cấp persistent storage cho pods
Dùng khi: Cần lưu trữ data bền vững
Các loại: PersistentVolume, EmptyDir, HostPath
Ví dụ phổ biến: Database storage, shared files

LivenessProbe

Kiểm tra container có đang hoạt động
Dùng khi: Cần auto-healing cho applications
Các method: HTTP, TCP, Command
Ví dụ phổ biến: Health check endpoints

ReadinessProbe

Kiểm tra pod đã sẵn sàng nhận traffic
Dùng khi: Cần đảm bảo service quality
Các method: HTTP, TCP, Command
Ví dụ phổ biến: Application startup checks

Nodes

Máy vật lý hoặc máy ảo trong cluster
Vai trò: Chạy pods và containers
Quản lý bởi: Kubelet
Ví dụ phổ biến: VM instances, physical servers
