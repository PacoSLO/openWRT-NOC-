## 🌐 OpenWrt Network Operations Center (NOC) Dashboard

A lightweight, modern, and responsive web-based dashboard designed to monitor your home network status in real-time. This project is built with minimal resource consumption in mind, making it ideal for running directly on **OpenWrt routers** (such as GL.iNet hardware) or within **Proxmox LXC containers** in a homelab environment.

---

## ⚠️ Disclaimer (Unofficial Project)

> **Important:** This is an independent, community-driven open-source hobby project. It is **NOT** an official application, nor is it endorsed, sponsored, or affiliated with OpenWrt, GL.iNet, Ookla, or any other official networking entities. Use it at your own discretion.

---

## ✨ Features

*   **Real-Time Traffic Monitoring:** Dynamic graphs displaying WAN download and upload bandwidth, refreshing automatically every 1.5 seconds.
*   **Hardware Overview:** Clean status cards for CPU usage, RAM utilization, and system Uptime of your main gateway.
*   **Client Statistics:** Overview of connected wired and wireless (Wi-Fi) clients, including active DHCP leases.
*   **Latency Tracker (Ping):** Live response times tracking to crucial external servers (e.g., Cloudflare 1.1.1.1, Google DNS 8.8.8.8).
*   **Speedtest Integration:** Trigger internet speed tests directly from the interface (powered by the Ookla speedtest-net backend).

---

## 🛠️ Tech Stack

*   **Frontend:** Clean HTML5, modern CSS3 (Grid & Flexbox layout), and Vanilla JavaScript (Fetch API, Chart.js).
*   **Backend:** Node.js with the Express framework for lightweight routing and API endpoints.

---

## 📸 Screenshots
<p align="center">
  <img src="https://i.imgur.com/8N4NshT.jpg" alt="OpenWrt NOC Dashboard Preview" width="900">
</p>

## 🚀 Quick Start Guide

### 1. Prepare the Directories
Connect to your device via SSH and create the project structure:

```bash
mkdir -p /opt/network-dashboard/public
cd /opt/network-dashboard
```

*  **Option A: Running directly on OpenWrt
```bash
opkg update
    opkg install node node-npm
```

*  **Option B: Running on Ubuntu/Debian (Proxmox LXC)**
```bash
    sudo apt update
    sudo apt install -y nodejs npm
```

### 4. Initialize Project & Install Dependencies
Navigate back to your project root folder, initialize the configuration file (`package.json`), and install the required dependencies:

```bash
cd /opt/network-dashboard

# Initialize a default package.json
npm init -y

# Install Express (The web server framework)
npm install express

# Install Speedtest-Net (The official Ookla Speedtest wrapper)
npm install speedtest-net

# Install PM2 globally
npm install -g pm2

# Start your server.js application
pm2 start server.js --name "network-dashboard"

# Save the process list and enable startup on boot
pm2 save
pm2 startup

🌐 Accessing the Dashboard
Once everything is up and running, open your favorite web browser and navigate to:

http://<YOUR_DEVICE_IP>:3000

Replace <YOUR_DEVICE_IP> with the local IP address of your router or LXC container (e.g., http://192.168.1.1:3000).

📝 License
This project is open-source and free to use. Feel free to fork it, modify it, and customize it to fit your personal homelab or home network setup.

