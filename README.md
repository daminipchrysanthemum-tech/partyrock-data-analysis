## 🌫️ Air Quality Data Analysis — Amazon Bedrock (PartyRock)

## 📌 Project Overview
This project analyzes 30 days of real-world air quality sensor data using **Amazon Bedrock's generative AI** via PartyRock. It explores pollution patterns, outlier days, and pollutant volatility — the same type of analytical workflow used in cloud-based IoT monitoring pipelines on AWS.

Built as part of a hands-on cloud learning project to demonstrate real-world data analysis using AWS AI services.

---

## 🛠️ Built With
- **Amazon Bedrock** — Generative AI foundation model (via PartyRock)
- **PartyRock** (partyrock.aws/data) — Amazon Bedrock's no-code data analysis playground
- **Dataset** — OpenAQ air quality sensor data (30 days, 6 pollutants, 737 readings)

---

## 📂 Dataset
| Field | Details |
|---|---|
| Source | OpenAQ (open-source air quality data) |
| Period | December 2025 – January 2026 (30 days) |
| Pollutants | PM2.5, PM10, CO, NO2, O3, SO2 |
| Total Readings | 666–737 per pollutant |
| File | `air-quality-data-set.csv` |

---

## ❓ Questions Asked & Key Findings

### 1. 🕐 Peak Pollution Hours
- **PM10** peaks at **5:00 PM** (32.97 µg/m³) — classic traffic pattern
- **PM2.5** peaks early morning **4–6 AM** — overnight accumulation
- **CO & NO2** peak at **4:00 PM** — rush hour vehicle emissions

### 2. 📅 Outlier Days
- **19 outlier days** identified across 30 days using z-score analysis
- Worst day: **January 1, 2026** — PM2.5 spiked 4.37 standard deviations above normal
- Multiple pollutants spiked together on Dec 23 & Jan 1, indicating systemic air quality events

### 3. 📊 Most Volatile Pollutant
- **PM10** is the most volatile (std dev: 11.25, swings of 30+ µg/m³ day-over-day)
- **NO2** shows the highest % volatility (53%), suggesting variable traffic/industrial patterns

### 4. 📋 30-Day Summary Table
| Pollutant | Avg | Min | Max | Std Dev |
|---|---|---|---|---|
| PM2.5 | 5.74 µg/m³ | 0.80 | 39.90 | 4.56 |
| PM10 | 19.49 µg/m³ | 2.00 | 106.00 | 15.83 |
| CO | 0.26 ppm | 0.00 | 1.10 | 0.20 |
| NO2 | 0.027 ppm | 0.003 | 0.133 | 0.023 |
| O3 | 0.021 ppm | 0.002 | 0.047 | 0.013 |
| SO2 | 0.0004 ppm | 0.00 | 0.0031 | 0.0004 |

---

## 🔗 Links
- 🤖 **PartyRock App (Cloud Architecture Advisor):** https://partyrock.aws/data
- 📁 **Dataset:** See [air-quality-data-set.csv](https://github.com/user-attachments/files/27190414/air-quality-data-set.csv) in this repo

---

## 💡 Cloud Connection
This analysis mirrors real AWS data workflows:
- IoT sensor ingestion → **AWS IoT Core + Kinesis**
- Overnight batch processing → **AWS Glue + Step Functions**
- Anomaly detection → **Amazon Lookout for Metrics**
- Dashboard delivery → **Amazon QuickSight**

---

## 📄 License
Data sourced from OpenAQ (open license). Analysis performed using Amazon Bedrock via PartyRock.
