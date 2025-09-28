# Phishing-SIM Scenario Report — TryHackMe

**Name:** Adam Abdelsalam Al-Himyri  
**Date:** 2025-09-25  
**Environment:** TryHackMe  
**Access Level:** Regular user account inside the Lab  
**Objective:** Evaluate the performance of the threat detection system (SIM/SIEM) for a specific scenario.

---

## Scope of the Report
- Total alerts to process: **53**  
- This report covers both **true positives** (legitimate detections) and **false positives** (benign alerts).

---

## Methodology / Steps Followed
1. Receive alert in the SIM — an alert is forwarded to the Security Operations Center (SOC).  
2. Open the alert details in the system to understand the activity.  
3. Investigate the domain using Splunk and search internal logs/databases.  
4. Verify files/processes using external tools such as VirusTotal.  
5. Classify the alert:
   - **False Positive:** benign / expected activity.  
   - **True Positive:** malicious activity → escalate and restrict access.  
6. Document findings and retain evidence for audit or legal purposes.

---

## Notable Cases

### Case 1 — Domain Alert
- **Indicator:** `online.headwearinnovations[.]com`  
- **Result:** Verified as legitimate.  
- **Classification:** **False Positive**

### Case 2 — Domain Alert
- **Indicator:** `com.tryhatm`  
- **Result:** Determined to be impersonation / malicious.  
- **Action:** **True Positive** — escalated and user access was restricted.

### Case 3 — Suspicious Process
- **Indicator:** `C:\Windows\servicing\TrustedInstaller.exe` executed with attempts to gain elevated privileges in violation of company policy.  
- **Classification:** **True Positive (Critical)**  
- **Action:** Report filed and the process activities were restricted.

---

## Final Statistics
- **Total alerts:** 53  
- **Processed:** 45  
- **True positives (malicious):** 33  
- **False positives (benign):** 12  
- **Elapsed time:** 113 minutes

---

## Recommendations
1. Avoid granting users unjustified elevated privileges.  
2. Continuously monitor suspicious activities via the SIEM.  
3. Report incidents to management to strengthen incident response.  
4. Preserve alert logs and evidence for legal review and auditing.

---
**Prepared by:** Adam Abdelsalam Al-Himyri
