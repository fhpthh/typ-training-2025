**1. Triển khai Kubernetes**
- Triển khai một Kubernetes Cluster gồm 1 Master node và 1 Worker node trên nền tảng Ubuntu 22.04.
- Lựa chọn triển khai **K3s – Lightweight Kubernetes**
- Mô hình hệ thống chuẩn bị:

| Node | Vai trò | Hệ điều hành | IP |
| :--- | :--- | :--- | :--- |
| master1 | K3s Server  | Ubuntu 22.04 | 192.168.126.102 |
| Worker 2 | K3S Worker | Ubuntu 22.04 | 192.168.126.100 |

- Cài đặt cơ bản:  

```
sudo apt update -y
sudo apt install -y curl 
```
- Cài đặt K3s (Master node):
  - SSH vào master node: ` ssh devops@192.168.126.102`
  - Cài đặt K3s: `curl -sfL https://get.k3s.io | sh`
  - Kiểm tra trạng thái: `systemctl status k3s`
  - Kiểm tra node: `sudo kubectl get nodes`
  
  ![alt txt](./images/bai1/statusk3s.png)

  - Lấy token để join Worker `sudo cat /var/lib/rancher/k3s/server/node-token`

- Cài đặt K3s Agent (Worker node):
  - SSH vào worker node `ssh worker@192.168.126.100`
  - Join worker vào cluster
  
  ![alt txt](./images/bai1/joinworker.png)

- Kiểm tra trạng thái: `sudo kubectl get nodes -o wide`

  ![alt txt](./images/bai1/result.png)
  
