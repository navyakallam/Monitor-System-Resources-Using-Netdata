# 🖥️ Monitor System Resources Using Netdata for DevOps

This project demonstrates how to install and run Netdata — a real-time monitoring tool — using Docker on an Ubuntu-based AWS EC2 instance. It helps visualize system and Docker container performance metrics.

---

## 🎯 Objective

To monitor system resources (CPU, memory, disk I/O, network, and Docker containers) in real-time using Netdata and explore logging for diagnostics.

---

## 🛠 Tools & Technologies Used

- 🐧 **Ubuntu (EC2)**
- 🐳 **Docker**
- 📊 **Netdata (Official Docker Image)**
- 📂 **Linux CLI Tools**

---

## ⚙️ Setup & Installation

### ✅ 1. Install Docker (if not already installed)

```
sudo apt update
sudo apt install docker.io -y
sudo systemctl start docker
sudo systemctl enable docker
sudo usermod -aG docker $USER
newgrp docker
```

### ✅ 2. Run Netdata via Docker

```
docker run -d --name=netdata -p 19999:19999 \
  --cap-add SYS_PTRACE \
  --security-opt apparmor=unconfined \
  netdata/netdata
```

---

## 🌐 Access the Netdata Dashboard

- **Local**: `http://localhost:19999`
- **Remote EC2**: `http://<your-ec2-public-ip>:19999`

📌 Ensure port **19999** is open in your EC2 security group.

---

## 📊 Features Explored

- ✅ Real-time **CPU, Memory, Disk I/O, Network** monitoring
- ✅ Docker container metrics
- ✅ Netdata alerts and thresholds
- ✅ Interactive charts & dashboard panels

---

## 📝 Logs

### ✅ Container Logs

```
docker logs netdata > Netdata_logs.txt
```

### ✅ Inside the Netdata Container

```
docker exec -it netdata bash
cd /var/log/netdata
ls
cat error.log
```
---

## 🧪 Output Screenshots

### 🔹 Netdata Dashboard
### 🔹 CPU and Memory Monitoring
### 🔹 Disk and Network I/O
### 🔹 Docker Container Running

## 📌 Learnings

- ✅ How to deploy Netdata using Docker
- ✅ Real-time system health monitoring
- ✅ Basic Linux and Docker administration
- ✅ Collecting and analyzing logs

---
**My live Netdata Monitoring Dashboard**  
    http://13.48.134.241:19999
