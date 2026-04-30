# 🌫️ Air Quality Data Analysis with Amazon Bedrock

> Analyzed 30 days of real-world air quality sensor data using **Amazon Bedrock (PartyRock)** — the same type of IoT telemetry workflow used in cloud-based environmental monitoring pipelines.

---

## 🛠️ Built With

- [Amazon Bedrock](https://aws.amazon.com/bedrock/) (PartyRock Analyze Data feature)
- **Dataset:** OpenAQ Air Quality Data — [air-quality-data-set.csv](./data/air-quality-dataset.csv)
- **Tools:** Whiskers AI, CSV data upload, natural language querying

---

## 🔍 Key Questions Explored

1. What are the peak pollution hours, and which pollutants spike the most?
2. Which days had significant air quality drops, and what patterns do outliers follow?
3. Which pollutant is most volatile day-over-day, and what does that mean operationally?
4. What do the 30-day min, max, and average values look like across all pollutants?

---

## 📊 Key Findings

- **PM10** is the most volatile pollutant, swinging 30+ µg/m³ day-over-day (41.5% volatility) — driven by traffic, wind-blown dust, and construction activity
- **Peak pollution** occurs at **5:00 PM** for PM10, which aligns with evening rush-hour traffic patterns
- **January 1, 2026** was the worst air quality day — PM2.5 spiked 4.37 standard deviations above normal, likely from New Year's fireworks and overnight atmospheric accumulation
- **NO2** showed the highest percentage volatility (53%), suggesting strong weekend vs. weekday traffic pattern effects
- Gaseous pollutants (CO, NO2, O3, SO2) remained well within safe ranges throughout the period
- Particulate matter is the **dominant air quality concern** at this location

> 📄 Full analysis with detailed question responses in [`findings/analysis-summary.md`](./findings/analysis-summary.md)

---

## 📋 30-Day Summary Table

| Pollutant | Avg | Min | Max | Std Dev |
|-----------|-----|-----|-----|---------|
| PM2.5 (µg/m³) | 5.74 | 0.80 | 39.90 | 4.56 |
| PM10 (µg/m³) | 19.49 | 2.00 | 106.00 | 15.83 |
| CO (ppm) | 0.26 | 0.00 | 1.10 | 0.20 |
| NO2 (ppm) | 0.027 | 0.003 | 0.133 | 0.023 |
| O3 (ppm) | 0.021 | 0.002 | 0.047 | 0.013 |
| SO2 (ppm) | 0.0004 | 0.00 | 0.0031 | 0.0004 |

---

## 📁 Repository Structure

```
air-quality-analysis-bedrock/
│
├── README.md
├── data/
│   └── air-quality-dataset.csv
└── findings/
    └── analysis-summary.md
```

---

## ☁️ Cloud Relevance

This analysis mirrors real-world cloud data workflows:

| Analysis Step | Equivalent AWS Service |
|---|---|
| IoT sensor ingestion | Amazon Kinesis / IoT Core |
| Batch processing | AWS Glue + Step Functions |
| Anomaly detection | Amazon CloudWatch Alarms |
| Dashboard reporting | Amazon QuickSight |

---

## 📁 Dataset

- **Source:** [OpenAQ](https://openaq.org)
- **Period:** December 2025 – January 2026
- **Readings:** 700+ per pollutant across 6 pollutant types
