# Raspberry Pi Monitoring System (Grafana + Prometheus)

This project is a complete Raspberry Pi–based monitoring appliance built using **Prometheus**, **Grafana**, and **Node Exporter**.  
It provides real-time system monitoring, network visibility, and device health metrics — similar to what is used in professional IT support and operations environments.

---

## 🚀 Features

- Real-time monitoring of CPU, memory, disk, network, and device uptime  
- Beautiful Grafana dashboards for visualization  
- Prometheus for metric collection and time-series storage  
- Node Exporter for system-level metrics on the Raspberry Pi  
- Docker Compose deployment for easy setup and management  
- Lightweight and efficient — ideal for Raspberry Pi 4 and Pi OS

---

## 📸 Screenshots

(Insert screenshots of your Grafana dashboard here)

---

## 🧰 Tech Stack

- Raspberry Pi OS  
- Docker & Docker Compose  
- Prometheus  
- Grafana  
- Node Exporter  

---

## 📁 Project Structure

.
├── docker-compose.yml

├── prometheus.yml

├── provisioning/

│ ├── dashboards/

│ │ └── example-dashboard.json

└── README.md

---

## ⚙️ Setup Instructions

### 1. Install Docker & Docker Compose

Run the official Docker install script:

curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh
sudo usermod -aG docker $USER

 Log out and back in.

### 2. Clone the Repository

git clone https://github.com/<your-username>/raspberrypi-monitoring.git
cd raspberrypi-monitoring

### 3. Start the Monitoring Stack

docker compose up -d

Grafana → http://<your-pi-ip>:3000
Prometheus → http://<your-pi-ip>:9090

⚠️ Important
This repository uses placeholder passwords for safety.
Replace <SET_PASSWORD_HERE> with secure values before running.

### 🔧 Configuration
Grafana Datasource (Prometheus)

If not automatically provisioned:

Open Grafana

Go to Configuration → Data Sources

Add Prometheus

URL: http://prometheus:9090

Click Save & Test

### Prometheus Scrape Config

Included in prometheus.yml:

scrape_configs:
  - job_name: 'node'
    static_configs:
      - targets: ['node-exporter:9100']

### 🔁 Automatic Startup on Reboot

Services in docker-compose.yml use:

restart: unless-stopped


This ensures Grafana, Prometheus, and Node Exporter automatically start whenever the Raspberry Pi reboots.

### 🧠 Why I Built This

I created this project to gain hands-on experience with:

Systems monitoring

Dockerized infrastructure

Linux server administration

Troubleshooting and incident response

Real-world IT tools used by support engineers

This project demonstrates practical skills relevant to IT, Desktop Support, and Systems roles.

📄 License

MIT License.
Feel free to use or modify this project for personal or educational purposes.
