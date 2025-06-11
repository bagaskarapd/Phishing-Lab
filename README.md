# Phishing-Lab

## Objective

This lab is based on the "Introduction to Phishing" scenario from TryHackMe's SOC Analyst Simulation. The goal was to analyze real-time alerts in a simulated SOC environment and identify phishing-related activity such as suspicious emails, malicious attachments, and command-and-control (C2) callbacks. The focus was on alert triage, incident documentation, and IOC extraction.

### Skills Learned

- Hands-on experience monitoring and closing alerts in a SOC environment.
- Analyzing email headers and metadata to detect phishing attempts.
- Identifying malicious links and attachments.
- Extracting Indicators of Compromise (IOCs) such as IP addresses, file hashes, and domains.
- Writing clear and concise incident response reports.
- Applying basic digital forensics principles during investigation.

### Tools Used

- **SOC Simulator (TryHackMe platform)** – to simulate real-time alerts.
- **Email Header Analyzer** – to extract and interpret metadata.
- **VirusTotal** – to analyze file hashes and URLs.
- **Any.run** – to investigate behavior of malicious attachments (remote execution analysis).
- **Text editor / markdown** – for documentation and incident reporting.

---

## Steps

### *Ref 1: Alert Overview*

![Alert Overview](https://i.imgur.com/alert1_example.png)  
> This is the main dashboard of the SOC simulator showing multiple alerts, including suspicious email and outbound connections to unknown IPs.

---

### *Ref 2: Email Header Analysis*

![Header Analysis](https://i.imgur.com/header_example.png)  
> Analysis of email header shows spoofed sender domain and base64-encoded PowerShell payload embedded in the email body.

---

### *Ref 3: Malicious Attachment (invoice.exe)*

![Malicious EXE](https://i.imgur.com/virustotal_example.png)  
> The attachment was uploaded to VirusTotal and detected as a variant of AnyDesk RAT. The SHA256 hash was flagged by multiple antivirus engines.

---

### *Ref 4: IOC Summary*

| Type       | Value                    | Description                            |
|------------|--------------------------|----------------------------------------|
| File Hash  | `4a7d1ed414474e4033ac29...` | Malicious .exe file attached to email  |
| URL        | `http://fake-invoice[.]xyz/invoice.exe` | Linked in phishing email |
| IP Address | `192.168.100.12`          | Destination for C2 traffic             |

---

### *Ref 5: Incident Report Snippet*

