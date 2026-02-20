# Phishing Email Analysis Project

## 📌 Project Overview
This project demonstrates a manual and technical analysis of a suspicious email to identify phishing indicators. The goal was to analyze the altered email address, mismatched URL and legitimacy of the mail using the 3 pillars of email authentication(SPF/DKIM/DMARC).

## 🛠️ Tools Used
* **Header Analysis:** [MXToolboc Header Analyzerr](https://mxtoolbox.com/EmailHeaders.aspx)
* **Visual Inspection:** Manual "Hover-over" technique for URL verification
* **Documentation:** GitHub Markdown for reporting

---

## 🔍 Methodology: How I Approached the Task

### 1. Initial Analysis of the Email Body
I began by reviewing the [Phishing sample.txt](./Phishing%20sample.txt), which says "Zonnepanelen voor een goede prijs" (Solar panels at a good price), to understand common "social engineering" red flags. I looked for:
* **Sense of Urgency:** Threats of account suspension.	
* **Generic Greetings:** Lack of a personalized name.
* **Grammar/Spelling:** Inconsistent branding or tone.

### 2. Identifying Sender Spoofing
I examined the "From" address and compared it against the "Return-Path" in the email metadata. I captured evidence of a mismatched domain, where the Yellow highlight explains that the email domain is serenitepure.fr. This is a French domain likely related to health/beauty ("sérénité pure"), which has absolutely nothing to do with solar panels in the Netherlands.
Whereas the Red underline path states the hidden address where "bounce" messages or errors are sent. It reveals the actual server that sent the mail i.e. a German domain (.de) email.![Sender Spoofing Evidence](./Header%20spoofing.png)

### 3. URL Verification (The Hover Test)

As documented in the screenshot below, the actual destination URL( http://go.nltrck.com ) did not match the official text "Klik hier voor 2 a 3 vrijblijvende offertes."
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
*Developed by [Devansh] | Cybersecurity Project*


