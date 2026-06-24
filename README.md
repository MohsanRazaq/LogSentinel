# LogSentinel

**LogSentinel** is a custom-built, Python-based security telemetry and log analysis engine designed to detect suspicious web activity through behavioral heuristics and structured event analysis.

---

## 🚀 Overview

LogSentinel transforms raw, noisy web server logs into high-fidelity security insights. It mimics the core logic of enterprise SIEM systems, allowing you to identify adversarial behavior such as vulnerability scanning, brute-force login attempts, and data exfiltration.

---

## 💡 Why I Built This

In the classroom, cybersecurity is often taught through the lens of offensive tradecraft—how to execute an exploit. However, the true complexity of the field lies in **Detection Engineering**. I built LogSentinel to demystify how SOC teams separate background noise from genuine malicious intent.

---

## 🛠️ How It Works

The engine processes logs via a structured pipeline:

1. **Ingestion:** Parses IPs, HTTP methods, status codes, and response sizes.
2. **Normalization:** Converts unstructured logs into queryable security events.
3. **Aggregation:** Groups events by IP to build a behavioral profile.
4. **Heuristic Analysis:** Evaluates patterns against temporal thresholds.
5. **Alerting:** Flags anomalies for investigation.

> **Data Flow:**
> `Raw Logs` $\rightarrow$ `Structured Events` $\rightarrow$ `Behavioral Aggregation` $\rightarrow$ `Security Alerts`

---

## 🔍 Detection Capabilities

| Feature | Logic | Security Value |
| --- | --- | --- |
| **Scanner Detection** | Tracks 404 error frequency per IP | Detects directory brute-forcing and automated recon. |
| **Brute-Force Detection** | Monitors POST requests to `/login` | Flags credential stuffing and password spraying. |
| **Data Exfiltration** | Monitors anomalous response sizes | Highlights potential unauthorized mass downloads. |

---

## 🏗️ Project Architecture

```text
[ Access Logs ]
      ↓
[ Parser Engine ]
      ↓
[ Normalized Telemetry ]
      ↓
[ Detection Engine ]
      ↓
[ Alert System ]

```

---

## 🛠️ Technologies Used

* **Language:** Python
* **Parsing:** Regex
* **Core Logic:** `defaultdict`, `datetime`
* **Design:** Structured telemetry modeling

---

## 🛣️ Future Roadmap

I am actively evolving LogSentinel to move beyond a monolithic script into a professional-grade telemetry pipeline:

* **Modular Architecture:** Decoupling the Parser, Detector, and Reporter into independent stages.
* **Persistent Storage:** Integrating **SQLite** for long-term event storage and historical correlation.
* **Advanced Analytics:** Implementing **Entropy-based anomaly detection** to catch obfuscated payloads.
* **Intelligence:** Developing a **Threat Scoring** system to prioritize alerts based on risk.
* **Scalability:** Adding cloud log ingestion capabilities.

---

## ⚠️ Disclaimer

LogSentinel is an educational project designed for learning the fundamentals of detection engineering and security automation. It is not intended to replace enterprise-grade SIEM or SOC infrastructure.

---
