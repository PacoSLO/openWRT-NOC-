# 🌐 OpenWrt Network Operations Center (NOC) Dashboard

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

## 🚀 Quick Start Guide

### 1. Prepare the Directories
Connect to your device via SSH and create the project structure:
```bash
mkdir -p /opt/network-dashboard/public
cd /opt/network-dashboard
