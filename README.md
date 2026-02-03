
<img width="1536" height="1024" alt="ChatGPT Image Feb 2, 2026, 09_38_03 PM" src="https://github.com/user-attachments/assets/14d6108e-7b68-40cc-b15c-df7a53b8632b" />

# Healthcare IT Operations Lab - Proof of Concept

> **A containerized demonstration of Healthcare IT + ITSM + Automation + GRC Compliance**

---

## 🎯 What This Demonstrates

This project showcases real-world healthcare IT operations skills:

- **Electronic Medical Records (EMR)** - OpenEMR system with patient data
- **IT Service Management (ITSM)** - osTicket help desk for incident tracking
- **Automation** - Python monitoring script that auto-creates tickets
- **Compliance Awareness** - HIPAA and NIST control mapping

**Tech Stack:** Docker, Python, MySQL, Linux, Web Applications

---

## 🏗️ Architecture Overview

```
┌─────────────────┐         ┌──────────────────┐         ┌─────────────────┐
│   OpenEMR       │         │  Bridge Script   │         │   osTicket      │
│  (EMR System)   │◄────────│  (Monitoring)    │────────►│ (Help Desk)     │
│                 │         │                  │         │                 │
│  Port 8081      │         │  Python + API    │         │  Port 8080      │
└─────────────────┘         └──────────────────┘         └─────────────────┘
        │                            │                            │
        └────────────────────────────┴────────────────────────────┘
                          Docker Network
```

**How It Works:**
1. OpenEMR serves as the electronic medical records system
2. Python script monitors OpenEMR health every few minutes
3. When OpenEMR goes down, script auto-creates a Priority 1 ticket in osTicket
4. IT team is immediately notified without waiting for user reports

---

## 📸 Component 1: OpenEMR - Electronic Medical Records

### Screenshot 1: OpenEMR Login Page

<img width="1274" height="750" alt="image" src="https://github.com/user-attachments/assets/b8247a80-cc9f-490a-b9c1-253adbedc914" />


---

### Screenshot 2: OpenEMR Patient Dashboard
<img width="746" height="539" alt="image" src="https://github.com/user-attachments/assets/bc5b5f5e-edfa-43a3-b108-fefd1399e189" />


10 synthetic patients loaded 

---

### Screenshot 3: Patient Record Detail

<img width="1259" height="657" alt="image" src="https://github.com/user-attachments/assets/ea748017-61bf-4ac8-9e5b-83ddd715e7dc" />


---

## 📸 Component 2: osTicket - IT Help Desk

### Screenshot 4: osTicket Admin Login

<img width="1269" height="842" alt="image" src="https://github.com/user-attachments/assets/e00229b9-e5f7-4425-be30-479480c4b130" />


---

### Screenshot 5: osTicket Dashboard

<img width="1239" height="897" alt="image" src="https://github.com/user-attachments/assets/b30f44f7-48fd-4b1a-a656-a5e583726fec" />


---

### Screenshot 6: Ticket Queue

<img width="1173" height="454" alt="image" src="https://github.com/user-attachments/assets/85a58a46-b97e-4c19-bcca-650993c2c036" />


---

## 📸 Component 3: Automated Monitoring (The Key Innovation)

### Screenshot 7: Bridge Script - Healthy Status

<img width="815" height="259" alt="image" src="https://github.com/user-attachments/assets/f4b2457a-965d-4351-ae29-063d52e0b512" />



---

### Screenshot 8: Simulated Outage

<img width="1464" height="150" alt="image" src="https://github.com/user-attachments/assets/b81d7bb4-9d22-483d-ad33-9b859a92f59f" />


---

### Screenshot 9: Automated Detection & Ticket Creation

<img width="1832" height="509" alt="image" src="https://github.com/user-attachments/assets/f3143eb2-e7aa-4f80-990f-dae786f38b1c" />

---

## 📸 Component 4: Compliance & Documentation

### Screenshot 10: GRC Control Mapping

<img width="1200" height="895" alt="image" src="https://github.com/user-attachments/assets/2d1396b6-3ab2-49a8-9cbf-66c30e7b2b97" />

---

### Screenshot 11: Project Documentation

<img width="1097" height="1008" alt="image" src="https://github.com/user-attachments/assets/5f5d543b-4140-4284-80f3-504151da170a" />


---

## 🎯 Key Takeaways

### Technical Skills Demonstrated
- ✅ **Docker & Containerization** - Multi-container orchestration
- ✅ **Python Development** - API integration, error handling, logging
- ✅ **Database Management** - MySQL, data import, queries
- ✅ **Linux/CLI** - Command line proficiency
- ✅ **Web Applications** - Understanding of web architecture

### Healthcare IT Knowledge
- ✅ **EMR Systems** - Hands-on with OpenEMR
- ✅ **Clinical Workflows** - Understanding patient data access needs
- ✅ **Downtime Impact** - Patient care continuity awareness
- ✅ **HIPAA Compliance** - Privacy and security requirements

### ITSM & Operations
- ✅ **Incident Management** - Automated detection and ticketing
- ✅ **Priority Assessment** - P1 for critical system outages
- ✅ **Service Monitoring** - Proactive health checks
- ✅ **Documentation** - Runbooks and procedures

### Soft Skills
- ✅ **Problem Solving** - Built solution from scratch
- ✅ **Initiative** - Self-directed learning project
- ✅ **Communication** - Clear documentation for non-technical audiences
- ✅ **Attention to Detail** - Compliance mapping and thorough testing

---

## 💼 Why This Matters for Healthcare IT

**The Problem:**
In healthcare, every minute of EMR downtime means doctors can't access patient records, nurses can't document care, and patient safety is at risk.

**Traditional Approach:**
1. System goes down
2. Clinical staff notice and call help desk
3. Help desk creates ticket
4. IT team is notified
5. **10-15 minutes wasted**

**This Solution:**
1. System goes down
2. Monitoring script detects it in seconds
3. Ticket auto-created with full context
4. IT team immediately notified
5. **Response time reduced to under 1 minute**

**Business Value:**
- Faster incident response = less patient care disruption
- Automated detection = no reliance on users reporting issues
- Detailed tickets = faster troubleshooting
- Compliance documentation = audit readiness

---

## 🚀 Technical Implementation Highlights

### Data Management
- Imported 10 synthetic patients with realistic demographics
- Created 5 staff users with role-based access
- All data HIPAA-compliant (completely fictional)

### Automation Logic
```python
# Simplified version of the monitoring logic
def check_health(url):
    response = requests.get(url)
    if response.status_code != 200:
        create_ticket(
            subject="[P1] OpenEMR Service Outage",
            priority="Critical",
            impact="Clinical staff cannot access patient records"
        )
```

### Infrastructure as Code
- Docker Compose for reproducible environments
- Environment variables for configuration
- Health checks and dependency management
- Persistent data volumes

---

## 🎓 What I Learned

### Technical Growth
- Deepened Docker expertise with multi-container applications
- Learned OpenEMR architecture and healthcare data models
- Practiced API integration and error handling
- Improved Python scripting and automation skills

### Domain Knowledge
- Understanding of EMR systems and clinical workflows
- HIPAA requirements and healthcare compliance
- Healthcare IT operational challenges
- Incident response in patient care environments

### Professional Skills
- Documentation for different audiences (technical and non-technical)
- Project organization and version control
- Problem-solving when encountering third-party dependency issues
- Balancing functionality with compliance requirements

---

## 🔮 Future Enhancements

If I were to expand this project:

1. **Enhanced Monitoring**
   - Database connectivity checks
   - API response time monitoring
   - Disk space and resource utilization

2. **Advanced Alerting**
   - PagerDuty integration for on-call notifications
   - Slack/Teams webhooks for team alerts
   - Email notifications with severity-based routing

3. **Metrics & Dashboards**
   - Grafana dashboard for uptime visualization
   - SLA compliance tracking
   - Mean time to resolution (MTTR) metrics

4. **Production Readiness**
   - SSL/TLS encryption
   - Secrets management (HashiCorp Vault)
   - Backup and disaster recovery procedures
   - High availability configuration

---

## 📄 License

This is a portfolio/demonstration project. All healthcare data is synthetic and fictional.

- OpenEMR: GNU GPL
- osTicket: GNU GPL
- Custom automation code: MIT License

