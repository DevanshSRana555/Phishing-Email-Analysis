# Phishing Email Analysis Project

## 📌 Project Overview
This project demonstrates a manual and technical analysis of a suspicious email to identify phishing indicators. The goal was to dissect the email's headers, body content, and embedded links to determine its legitimacy and intent.

## 🛠️ Tools Used
* **Header Analysis:** [Google Admin Toolbox MessageHeader](https://toolbox.googleapps.com)
* **Visual Inspection:** Manual "Hover-over" technique for URL verification
* **Documentation:** GitHub Markdown for reporting

---

## 🔍 Methodology: How I Approached the Task

### 1. Initial Analysis of the Email Body
I began by reviewing the [Phishing sample.txt](./Phishing%20sample.txt) for common "social engineering" red flags. I looked for:
* **Sense of Urgency:** Threats of account suspension.
* **Generic Greetings:** Lack of a personalized name.
* **Grammar/Spelling:** Inconsistent branding or tone.

### 2. Identifying Sender Spoofing
I examined the "From" address and compared it against the "Return-Path" in the email metadata. I captured evidence of a mismatched domain which confirmed the sender was impersonating a legitimate brand.
![Sender Spoofing Evidence](./Header%20spoofing.png)

### 3. URL Verification (The Hover Test)
Before clicking any buttons, I performed a "hover test" on the call-to-action. As documented in the screenshot below, the actual destination URL did not match the official website of the company.
![Mismatched URL Evidence](./Mismatched%20URL.png)

### 4. Technical Header Breakdown
To confirm my suspicions, I ran the raw email headers through a professional analyzer. The results showed **SPF and DKIM failures**, meaning the email originated from an unauthorized server.
![Technical Header Analysis](./Header%20Analyzer%20result.png)

---

## 💡 Conclusion & Key Takeaways
Based on the **authentication failures** and **malicious redirects** identified, I classified this email as a **Credential Theft (Phishing)** attempt.

**Lessons Learned:**
* Never trust the display name in the "From" field.
* Always verify the technical headers (SPF/DKIM) before interacting with attachments.
* Use the "Hover-over" rule for every link to prevent redirection to malicious domains.

---
*Developed by [Your Name] | Cybersecurity Beginner Project*
