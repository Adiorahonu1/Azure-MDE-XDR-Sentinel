# 🔐 Azure Endpoint Security and SIEM Integration Project

This project showcases a practical implementation of **Microsoft Defender for Endpoint (MDE)** and **Microsoft Sentinel**. I onboarded four virtual machines—one **Windows Jump-Server** and three **Linux-based servers** (Web, App, and DB)—to MDE. These endpoints were integrated with Sentinel to enable real-time threat detection, analysis, and response.

---

## 📁 Project Structure

- 🪟 **Jump-Server** (Windows VM)  
- 🐧 **Web-Server** (Linux VM)  
- 🐧 **App-Server** (Linux VM)  
- 🐧 **DB-Server** (Linux VM)

---

## ✅ Step 1: Onboarding VMs to Microsoft Defender for Endpoint

Each VM was onboarded using platform-specific methods:

- **Windows VM:** Onboarded using a local script from the Microsoft 365 Defender onboarding package.  
- **Linux VMs:** Onboarded using terminal commands with the Linux onboarding script.

### 📸 Screenshots to Include

1. **Defender onboarding package (Windows)**  
2. **Linux onboarding script execution**  
3. **Devices listed in Microsoft 365 Defender portal**

   
 <img src="assets/Screenshot 2025-04-09 at 11.42.25.png" width="300"> <img src="assets/Screenshot 2025-04-09 at 12.37.33.png" width="300"> <img src="assets/Screenshot 2025-04-09 at 11.41.01.png" width="300"> <img src="assets/Screenshot 2025-04-09 at 11.41.49.png" width="300">  <img src="assets/Screenshot 2025-04-09 at 11.42.04.png" width="300">
---

## 🔒 Step 2: Simulating a Safe Threat for Detection

To verify threat detection, I used the **EICAR test file**, a harmless antivirus test string that simulates malware.

### ▶️ Windows EICAR Test

```powershell
echo "X5O!P%@AP[4\PZX54(P^)7CC)7}$EICAR-STANDARD-ANTIVIRUS-TEST-FILE!$H+H*" > C:\Users\Public\eicar.com
```

- Defender flagged the file immediately as a threat.
- Alerts appeared in the **Microsoft 365 Defender portal** under:
  - Alerts  
  - Device Timeline  
  - Incidents  

### 📸 Screenshots to Include

4. **EICAR detection alert in Defender portal**  
5. **Alert details and incident view**


    <img src="assets/Screenshot 2025-04-09 at 19.33.27.png" width="300"> <img src="assets/Screenshot 2025-04-10 at 15.35.56.png" width="300"> <img src="assets/Screenshot 2025-04-09 at 18.46.24.png" width="300"> <img src="assets/Screenshot 2025-04-09 at 18.50.27.png" width="300"> <img src="assets/Screenshot 2025-04-09 at 19.26.31.png" width="300"> 

---

## 📡 Step 3: Integration with Microsoft Sentinel

Microsoft Defender for Endpoint data was connected to Microsoft Sentinel for enhanced detection and response.

### 🔧 Actions Taken

- Enabled **Microsoft Defender for Endpoint connector** in Sentinel  
- Enabled **log ingestion** into the Log Analytics workspace  
- Configured rule to **automatically create incidents** from Defender alerts  

### 📸 Screenshots to Include

6. **Sentinel connector setup**  
7. **Alerts flowing into Sentinel**  
8. **Incident creation rule in Sentinel**

   <img src="assets/Screenshot 2025-04-10 at 15.42.31.png" width="300"> <img src="assets/Screenshot 2025-04-10 at 15.42.55.png" width="300"> <img src="assets/Screenshot 2025-04-10 at 15.44.20.png" width="300"> <img src="assets/Screenshot 2025-04-09 at 19.40.11.png" width="300"> 



---

## 📈 Use Case: Incident Detection and Correlation

Using the rule *"Create incidents based on Microsoft Defender for Endpoint alerts"*, Sentinel automatically generated incidents from simulated threats.

### 🧐 Observations

- Immediate alert creation from EICAR test  
- Incident correlation in Sentinel  
- Visibility into device timeline and user activity  

### 📸 Screenshots to Include

9. **Sentinel incident view**  
10. **Investigation graph showing affected host and alert chain**

<img src="assets/Screenshot 2025-04-10 at 11.28.44.png" width="300"> <img src="assets/Screenshot 2025-04-10 at 11.33.33.png" width="300"> <img src="assets/Screenshot 2025-04-10 at 11.34.07.png" width="300">
---

## 🎯 Key Security Capabilities Demonstrated

✅ Endpoint onboarding (Windows & Linux)  
✅ Threat simulation and validation  
✅ Real-time alert and incident generation  
✅ Centralized visibility and investigation using Sentinel  

---

## 📎 Conclusion

This hands-on project demonstrates how to build a **secure and observable cloud environment** using Microsoft Defender for Endpoint and Microsoft Sentinel. The exercise validated:

- Real-time detection and response  
- Integration between endpoint protection and SIEM tools  
- Microsoft security tooling across a **multi-OS infrastructure**

---

## 🖼️ Screenshots

All related screenshots are stored in the `/assets` directory and are referenced throughout this documentation.

---

## 🔗 Resources

- [Microsoft Defender for Endpoint Documentation](https://learn.microsoft.com/en-us/microsoft-365/security/defender-endpoint/)  
- [Microsoft Sentinel Documentation](https://learn.microsoft.com/en-us/azure/sentinel/)  
- [EICAR Test File Information](https://www.eicar.org/?page_id=3950)
