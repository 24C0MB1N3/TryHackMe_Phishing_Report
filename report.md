# **Blue Team Incident Report**
**Date:** 2025-11-29  
**Investigator:** Zaid Ben Omar  
**MITRE ATT&CK Technique:** T1566 – Phishing

---

## **Overview**
Multiple employees at *thetrydaily.thm* received phishing emails attempting to lure them into credential-harvesting websites. Two unique phishing themes were identified: a fake Microsoft login alert and a fake Amazon delivery notification. One alert was deemed a false positive.

---

## **Affected Users**

### **1. c.allen@thetrydaily.thm**  
**Timestamp:** 2025-11-29 15:05:51.369  
**Phishing Theme:** Unusual sign-in attempt  
**Malicious Payload:** Fake Microsoft login page  
**URL:** `https://m1crosoftsupport.co/login`  
**Assessment:**  
The URL impersonates Microsoft by substituting letters. Clear credential-harvesting intent.

---

### **2. h.harris@thetrydaily.thm**  
**Timestamp:** 2025-11-29 16:29:03.729  
**Phishing Theme:** Undelivered package notification  
**Malicious Payload:** Fake Amazon delivery page  
**URL:** `http://bit.ly/3sHkX3da12340`  
**Assessment:**  
Shortened URL likely redirects to a fraudulent Amazon lookalike page designed to steal user information.

---

### **3. j.garcia@thetrydaily.thm**  
**Status:** False Positive  
No malicious indicators detected.

---

## **Indicators of Compromise (IOCs)**

| Type | Indicator |
|------|-----------|
| Malicious Domain | `m1crosoftsupport.co` |
| Malicious URL | `https://m1crosoftsupport.co/login` |
| Shortened URL | `http://bit.ly/3sHkX3da12340` |

---

## **Impact**
Potential credential compromise if users entered login details on phishing pages. No confirmed compromise at time of reporting.

---

## **Recommendations**

### **Immediate Actions**
- **Block all inbound emails** associated with the following domains/URLs:  
  - `m1crosoftsupport.co`  
  - `https://m1crosoftsupport.co/login`  
  - `bit.ly/3sHkX3da12340`  

- **Block outbound traffic** to:  
  - `m1crosoftsupport.co`  
  - Any resolved destination of `bit.ly/3sHkX3da12340`

### **User Awareness**
- Notify affected employees about this phishing attempt.  
- Remind staff to verify suspicious login alerts and delivery notifications.

### **Security Enhancements**
- Enable URL rewriting & sandboxing on mail gateway.  
- Improve SPF, DKIM, and DMARC enforcement.  
- Increase frequency of simulated phishing campaigns for awareness training.

---

## **Conclusion**
Two phishing attempts were detected and mitigated. No evidence of credential compromise. Block rules implemented and awareness actions recommended to prevent recurrence.

---
