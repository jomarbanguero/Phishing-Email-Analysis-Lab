# Phishing Email Analysis Lab
### Python-Based Email Security Investigation & Automated Phishing Detection

## Project Overview

This project demonstrates a hands-on phishing email investigation using Python, email header analysis, and automated security detection techniques.

I developed a Python-based email analyzer that examines simulated email messages, extracts important header information, identifies suspicious indicators, assigns risk scores, and automatically generates investigation reports.

The goal of this project was to gain practical experience with email security, phishing detection, security analysis, and Python automation.

**Note:** All email samples, domains, and authentication results used in this project are fictional and intended for educational purposes.

---

## 🛠️ Technologies & Tools Used

- **Python 3:** Email parsing, automation, and risk scoring
- **Visual Studio Code:** Development and testing
- **Email Security:** SPF, DKIM, and DMARC interpretation
- **Python Standard Library:** Email parsing, regular expressions, and URL analysis
- **GitHub:** Version control and project documentation
- **Markdown:** Automated security investigation reports

## Project Objectives

- Investigate simulated phishing emails.
- Examine email headers and sender information.
- Identify suspicious links and phishing indicators.
- Interpret supplied SPF, DKIM, and DMARC results.
- Develop a Python tool to automate email analysis.
- Implement rule-based risk scoring.
- Generate automated investigation reports.
- Test and document the analyzer's functionality.

---

# Phase 1 — Lab Setup & Email Sample Collection

The first phase involved creating a structured environment for investigating suspicious emails.

I organized the project into separate folders for email samples, investigation reports, and screenshots.

Three fictional email scenarios were created:

| Email | Scenario | Purpose |
|---|---|---|
| Email 01 | Password Expiration Notice | Simulate credential phishing |
| Email 02 | Failed Package Delivery | Simulate delivery-related phishing |
| Email 03 | Employee Handbook Update | Provide a lower-concern comparison sample |

## 1.1 Lab Environment Setup

The project was organized into folders to keep email samples, reports, and investigation evidence separate.

** SCREENSHOT 1 — LAB FOLDER STRUCTURE**

**What to upload:** A screenshot of VS Code showing the `samples`, `reports`, and `screenshots` folders.

**Save as:** `01-lab-structure.png`

![Screenshot 1 - Lab Folder Structure](screenshots/01-lab-structure.png)

## 1.2 Suspicious Email Sample

The first email claimed to originate from an IT support department and instructed the recipient to verify their account immediately.

The message contained urgency, an account suspension warning, and an external verification link.

**📸 SCREENSHOT 2 — SUSPICIOUS EMAIL SAMPLE**

**What to upload:** A screenshot of `email_01.txt` showing the suspicious message, account verification request, and external link.

**Save as:** `02-phishing-email-analysis.png`

![Screenshot 2 - Suspicious Email](screenshots/02-phishing-email-analysis.png)

---

# Phase 2 — Email Header Analysis & Investigation

The second phase focused on manually examining email headers to identify suspicious characteristics.

I investigated:

- **From:** Displayed sender address
- **Reply-To:** Address where replies are directed
- **Return-Path:** Envelope sender address
- **Received:** Email routing information
- **Authentication-Results:** Supplied SPF, DKIM, and DMARC results
- **Message-ID:** Email identifier

## 2.1 Email Header Investigation

I examined the relationship between sender addresses, reply-to domains, authentication results, and message content.

** SCREENSHOT 3 — EMAIL HEADER ANALYSIS**

**What to upload:** A screenshot of `email_01.txt` displaying its `From`, `Reply-To`, `Return-Path`, and `Authentication-Results` headers.

**Save as:** `03-email-header-analysis.png`

![Screenshot 3 - Email Header Analysis](screenshots/03-email-header-analysis.png)

## 2.2 Identifying Phishing Indicators

The investigation focused on several indicators commonly associated with phishing:

- Urgent account verification requests
- Threats of account suspension
- Sender and reply-to domain differences
- External links
- Supplied authentication failures
- Requests for sensitive information

** SCREENSHOT 4 — PHISHING INVESTIGATION FINDINGS**

**What to upload:** A screenshot of the Markdown preview of `reports/email_02_analysis.md` showing the suspicious indicators and authentication findings.

**Save as:** `04-phishing-findings.png`

![Screenshot 4 - Phishing Findings](screenshots/04-phishing-findings.png)

## 2.3 Manual Investigation Summary

Each email was evaluated based on its available headers and message content.

Emails 01 and 02 demonstrated phishing-like characteristics, while Email 03 contained fewer suspicious indicators.

** SCREENSHOT 5 — INVESTIGATION SUMMARY**

**What to upload:** A screenshot of the Markdown preview of `reports/investigation_summary.md` showing the comparison table for all three emails.

**Save as:** `05-investigation-summary.png`

![Screenshot 5 - Investigation Summary](screenshots/05-investigation-summary.png)

---

# Phase 3 — Python Phishing Email Analyzer

The third phase involved developing a Python program to automate the email investigation process.

I created `email_analyzer.py`, which reads email samples, extracts header information, identifies predefined suspicious indicators, and assigns risk scores.

## 3.1 Python Analyzer Development

The analyzer was built using Python's standard library.

### Key Features

- Reads email files from the `samples` directory
- Extracts sender addresses and subjects
- Identifies sender and reply-to domain mismatches
- Interprets supplied SPF, DKIM, and DMARC results
- Detects predefined urgency language
- Identifies URLs using domains different from the sender
- Calculates heuristic risk scores
- Generates automated Markdown investigation reports

** SCREENSHOT 6 — PYTHON ANALYZER CODE**

**What to upload:** A screenshot of `email_analyzer.py` in VS Code showing the detection rules, risk scoring logic, and classification thresholds.

**Save as:** `06-python-analyzer.png`

![Screenshot 6 - Python Analyzer](screenshots/06-python-analyzer.png)

## 3.2 Automated Email Investigation

After developing the analyzer, I executed it against the three fictional email samples.

The program identified configured phishing indicators and calculated a risk score for each message.

** SCREENSHOT 7 — AUTOMATED DETECTION RESULTS**

**What to upload:** A screenshot of the VS Code terminal after running `python3 email_analyzer.py`, showing the three emails and their risk scores.

**Save as:** `07-detection-results.png`

![Screenshot 7 - Detection Results](screenshots/07-detection-results.png)

## 3.3 Automated Investigation Reporting

The Python program generates a structured Markdown report containing:

- Email filename and subject
- Sender and reply-to information
- Supplied SPF, DKIM, and DMARC results
- Detected suspicious indicators
- Risk scores and classifications

The report is saved at:

`reports/automated_analysis.md`

** SCREENSHOT 8 — AUTOMATED INVESTIGATION REPORT**

**What to upload:** A screenshot of `automated_analysis.md` in Markdown Preview, showing the automated summary table.

**Save as:** `08-automated-report.png`

![Screenshot 8 - Automated Report](screenshots/08-automated-report.png)

---

# Phase 4 — Testing, Validation & Final Results

The final phase focused on validating the analyzer and confirming that its detection logic responded to changes in email headers.

I tested the analyzer using the original email samples and performed a controlled modification to the `Reply-To` field of Email 03.

The modified header caused the analyzer to identify a domain mismatch and increase its risk score.

After restoring the original email, I executed the analyzer again to verify the baseline results.

## 4.1 Final Investigation Results

| Email | Risk Score | Classification |
|---|---:|---|
| Email 01 — Password Expiration | 6 | High Concern |
| Email 02 — Failed Delivery | 11 | High Concern |
| Email 03 — Employee Handbook | 0 | Low Concern |

### Results Analysis

**Email 01 — High Concern**

The analyzer identified an urgent credential verification request, a reply-to domain mismatch, and an external verification link.

**Email 02 — High Concern**

The analyzer identified supplied SPF and DMARC failures, urgency language, a reply-to domain mismatch, and an external link.

**Email 03 — Low Concern**

The original comparison sample contained none of the analyzer's configured suspicious indicators.

These results are educational risk classifications rather than confirmed malicious activity.

## 4.2 Final Validation

The final test confirmed that the analyzer processed all three sample emails and generated the expected risk classifications.

**📸 SCREENSHOT 9 — FINAL VALIDATION TEST**

**What to upload:** A screenshot of the terminal after the final successful run, showing scores of 6, 11, and 0.

**Save as:** `09-validation-test.png`

![Screenshot 9 - Final Validation](screenshots/09-validation-test.png)

---

# 📊 Key Findings

### Email Authentication

An email can pass SPF or DMARC authentication and still contain suspicious content.

### Sender and Reply-To Analysis

Different sender and reply-to domains can warrant further investigation, but they do not automatically indicate phishing.

### Social Engineering Indicators

Urgent deadlines, account suspension warnings, and requests for sensitive information can indicate phishing attempts.

### Python Security Automation

The analyzer demonstrates how repetitive email investigation tasks can be automated using predefined detection rules.

### Security Documentation

Structured reports help explain findings and communicate security assessments.

---

# How to Run the Project

## Requirements

- Python 3
- Terminal or Visual Studio Code
- No additional Python packages required

## Installation

**1. Clone the repository:**

```bash
git clone https://github.com/jomarbanguero/Phishing-Email-Analysis-Lab.git
```

**2. Navigate to the project folder:**

```bash
cd Phishing-Email-Analysis-Lab
```

**3. Run the analyzer:**

```bash
python3 email_analyzer.py
```

**4. Review the results:**

The program displays findings in the terminal and generates a report at:

`reports/automated_analysis.md`

---

# Project Structure

```text
Phishing-Email-Analysis-Lab/
├── README.md
├── email_analyzer.py
├── .gitignore
│
├── samples/
│   ├── email_01.txt
│   ├── email_02.txt
│   └── email_03.txt
│
├── reports/
│   ├── email_01_analysis.md
│   ├── email_02_analysis.md
│   ├── email_03_analysis.md
│   ├── investigation_summary.md
│   └── automated_analysis.md
│
└── screenshots/
    ├── 01-lab-structure.png
    ├── 02-phishing-email-analysis.png
    ├── 03-email-header-analysis.png
    ├── 04-phishing-findings.png
    ├── 05-investigation-summary.png
    ├── 06-python-analyzer.png
    ├── 07-detection-results.png
    ├── 08-automated-report.png
    └── 09-validation-test.png
```

---

# Project Limitations

- All email samples and authentication results are fictional.
- The analyzer does not independently validate SPF, DKIM, or DMARC.
- Risk scores are educational heuristics, not validated threat probabilities.
- A low-concern classification does not guarantee safety.
- Domain differences alone do not establish malicious intent.
- The analyzer does not visit suspicious links or execute attachments.

---

# Skills Demonstrated

**Cybersecurity**
- Phishing email
