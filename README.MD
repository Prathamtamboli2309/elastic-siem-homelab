# 🚀 Elastic SIEM Implementation Using Docker for Centralized Log Monitoring

This project demonstrates how to deploy a complete **SIEM (Security Information and Event Management)** solution using the **Elastic Stack** on a Windows machine.  
It includes Elasticsearch, Kibana, Winlogbeat, and optional Elastic Agent for log collection and monitoring.

---

# 📌 1. Introduction

Today’s operating systems generate an enormous amount of logs. Monitoring all these logs manually is nearly impossible.

This project solves that by building a **Centralized SIEM** using:

- **Elastic Stack (Elasticsearch + Kibana)**
- **Docker (for easy deployment)**
- **Winlogbeat (for Windows Event Log collection)**

### 🎯 Goals:
- Collect logs from multiple endpoints  
- Visualize logs using dashboards  
- Detect security events through alerts  
- Build real-world SOC-style monitoring  

This project showcases skills in:
- Log management  
- Security monitoring  
- Docker administration  
- Detection engineering  
- SIEM dashboards & alerting  

---

# ⚙️ 2. Tools and Technologies Used

### **2.1 Docker**
Runs Elasticsearch and Kibana inside isolated containers.

### **2.2 Elasticsearch**
Stores and indexes all incoming logs.

### **2.3 Kibana**
Provides dashboards, log search, alerts, and SIEM security insights.

### **2.4 Filebeat / Winlogbeat**
Lightweight agents used to ship logs:
- Filebeat → Linux/Mac  
- Winlogbeat → Windows Event Logs  

### **2.5 Elastic Agent (Optional)**
Unified monitoring agent for logs, metrics, and security events.

### **2.6 Docker Compose**
Used to run multiple containers together with a single configuration file.

---

# 🧱 3. Project Architecture

### **3.1 Elastic Stack (Core SIEM Platform)**
- **Elasticsearch:** Stores logs  
- **Kibana:** Visualizes logs & security events  
- Both run inside Docker containers

### **3.2 Log Collection Agents**
Agents installed on endpoints:
- Winlogbeat (Windows)
- Filebeat (Linux/Mac)
- Elastic Agent (optional)

Collects:
- System events  
- Authentication logs  
- Application logs  
- Error/warning logs  

### **3.3 Data Flow**
1. Endpoints generate logs  
2. Beats/Agents read logs  
3. Logs forwarded to Elasticsearch  
4. Kibana visualizes logs & alerts  

### **3.4 Dashboards & Alerts Layer**
Kibana SIEM provides:
- Host activity dashboards  
- Authentication trends  
- Alert rules (failed logins, suspicious actions, etc.)

### **3.5 Multi-Host Monitoring**
Multiple endpoints forwarding logs → real SOC-like environment.

---

# 🛠️ 4. Setup & Implementation Steps

## 🔹 4.1 Install Docker Desktop (Windows)

### Step 1 — Download  
https://www.docker.com/products/docker-desktop/

### Step 2 — Install
- Run installer  
- Enable **WSL2**  
- Restart PC  

### Step 3 — Verify Docker
Open PowerShell (Admin):

```powershell
docker --version
docker compose version
