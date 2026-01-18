# 1. Triển khai Kubernetes
- Triển khai một Kubernetes Cluster gồm 1 Master node và 1 Worker node trên nền tảng Ubuntu 22.04.
- Lựa chọn triển khai **K3s – Lightweight Kubernetes**
- Mô hình hệ thống chuẩn bị:

| Node | Vai trò | Hệ điều hành | IP |
| :--- | :--- | :--- | :--- |
| master1 | K3s Server  | Ubuntu 22.04 | 192.168.126.102 |
| worker | K3S Worker | Ubuntu 22.04 | 192.168.126.100 |

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

# 2. Triển khai web application sử dụng các DevOps tools & practices
## K8S Helm Chart (1.5đ)
**2.1. Yêu cầu 1**
- **Cài đặt ArgoCD** lên Kubernetes Cluster, expose được qua ArgoCD qua NodePort
  - Tạo namespace và triển khai bằng cách áp dụng các file từ chính kho lưu trưc của dự án Argi Project:
  ```bash
  kubectl create namespace argocd

  kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml

  ```
 ![alt txt](./images/argo/setup.png)

  ![alt txt](./images/argo/pods.png)

  - Expose qua NodePort
  ```bash
  kubectl patch svc argocd-server -n argocd -p '{"spec":{"type":"NodePort"}}'
  ```

   ![alt txt](./images/argo/nodeport.png)

 - Lấy mật khẩu:
 ```bash
 kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d
 ```

 - Kết quả:
 ![alt txt](./images/argo/login.png)

  ![alt txt](./images/argo/result.png)

- **Cài đặt Jenkins** lên Kubernetes Cluster, expose được Jenkins qua NodePort
