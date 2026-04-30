## 📊 Full Analysis Summary — Air Quality Data

> Generated using Amazon Bedrock (PartyRock Analyze Data)
> Dataset: OpenAQ | Period: December 2025 – January 2026 | 700+ readings across 6 pollutants

---

## Question 1: Peak Pollution Hours & Pollutants That Spike Most

Peak hours vary significantly by pollutant:

| Pollutant | Peak Hour | Peak Value | Pattern |
|---|---|---|---|
| PM10 | 5:00 PM (hour 17) | 32.97 µg/m³ avg | Evening traffic |
| PM2.5 | 4:00–6:00 AM | 9.38–9.18 µg/m³ | Overnight accumulation |
| CO | 4:00 PM | 0.46 ppm | Afternoon traffic |
| NO2 | 4:00 PM | 0.053 ppm | Vehicle emissions |
| O3 | 10:00–11:00 PM | 0.036–0.037 ppm | Photochemical accumulation |
| SO2 | 4:00 PM | 0.0009 ppm | Extremely low throughout |

**Key finding:** PM10 and PM2.5 show the most significant spikes, with PM10 reaching values over 100 µg/m³ during peak hours. The 5 PM PM10 peak is a 
textbook traffic-related particulate pattern.

---

## Question 2: Days with Significant Air Quality Drops & Outlier Patterns

Using statistical analysis (z-scores > 1.5), 19 outlier days were identified across the 30 days.

### Worst Air Quality Days

**January 1, 2026** — Most severe day overall
- PM2.5 spiked to 22.5 µg/m³ — **4.37 standard deviations** above normal
- CO reached 0.58 ppm (2.91 SD above normal)
- PM10 elevated at 44.1 µg/m³
- Likely cause: New Year's fireworks + overnight atmospheric accumulation

**December 18, 2025**
- PM10 hit 51.1 µg/m³ (2.89 SD above normal)
- Max reading reached 94 µg/m³

**December 23, 2025** — Multiple pollutants elevated simultaneously
- CO at 0.48 ppm
- NO2 at 0.048 ppm
- PM10 at 38.7 µg/m³

### Outlier Patterns Observed

- Particulate matter (PM10/PM2.5) dominates the worst days — suggesting dust, smoke, or stagnant air
- Multiple pollutants spiking together on certain days (January 1, December 23) indicate **systemic air quality events**
- SO2 shows an opposite pattern — unusually LOW readings on Dec 13, 14, 18, 27, suggesting variable industrial activity or wind patterns
- Poor air quality days cluster in early December and late December/early January

---

## Question 3: Most Volatile Pollutant & Operational Implications

**PM10 is by far the most volatile pollutant.**

| Pollutant | Std Dev | Avg Daily Change | Max Increase | Max Decrease | % Volatility |
|---|---|---|---|---|---|
| PM10 | 11.25 | 8.37 µg/m³ | +25.92 µg/m³ | -32.29 µg/m³ | 41.5% |
| PM2.5 | 3.89 | 2.66 µg/m³ | +16.04 µg/m³ | -5.78 µg/m³ | 43.1% |
| CO | 0.14 | 0.11 ppm | +0.30 ppm | -0.28 ppm | 39.9% |
| NO2 | 0.02 | 0.01 ppm | +0.04 ppm | -0.03 ppm | 53.1% |

### Operational Implications

**PM10's extreme volatility (swings of 30+ µg/m³ day-over-day) suggests:**
- Weather-dependent sources: wind-blown dust, construction, or agricultural operations
- Need for real-time monitoring — conditions can deteriorate rapidly
- Difficult to predict: high variability makes forecasting challenging

**NO2's high percentage volatility (53%) despite lower absolute values indicates:**
- Variable traffic patterns or industrial activity
- Weekend vs. weekday effects likely present
- Sensitive to operational changes

**PM2.5's moderate volatility** suggests more stable combustion sources (heating, vehicles) compared to PM10's mechanical sources (dust, construction).

### Cloud Monitoring Parallel
In an AWS context, PM10's volatility pattern is analogous to a workload metric that requires **dynamic CloudWatch alarms with anomaly detection** rather 
than static thresholds — because the baseline itself shifts significantly day to day.

---

## Question 4: 30-Day Summary Statistics

| Pollutant | Units | Total Readings | Average | Min | Max | Std Dev | Range |
|---|---|---|---|---|---|---|---|
| PM2.5 | µg/m³ | 737 | 5.74 | 0.80 | 39.90 | 4.56 | 39.10 |
| PM10 | µg/m³ | 737 | 19.49 | 2.00 | 106.00 | 15.83 | 104.00 |
| CO | ppm | 727 | 0.26 | 0.00 | 1.10 | 0.20 | 1.10 |
| NO2 | ppm | 666 | 0.027 | 0.003 | 0.133 | 0.023 | 0.130 |
| O3 | ppm | 728 | 0.021 | 0.002 | 0.047 | 0.013 | 0.045 |
| SO2 | ppm | 689 | 0.0004 | 0.00 | 0.0031 | 0.0004 | 0.0031 |

### Key Insights from the Summary Table

- **PM10** shows the widest range (104 µg/m³) and highest variability — confirming it as the most problematic pollutant at this location
- **PM2.5** averages 5.74 µg/m³, well below the EPA's 24-hour standard of 35 µg/m³, but peaks at 39.9 µg/m³ — occasionally exceeding safe thresholds
- **Gaseous pollutants** (CO, NO2, O3, SO2) remain relatively low and within safe ranges throughout the entire period
- **SO2 is negligible** throughout, suggesting minimal industrial sulfur emissions at this location
- This location's primary air quality concern is **particulate matter**, with traffic and dust as the likely dominant sources
