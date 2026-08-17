# Sleep Analysis Dataset Processing & Findings

This project analyzes the relationships between mammalian physical attributes, developmental metrics, environmental threats, and total daily sleep duration. 

## Overview
Using a dataset of mammalian species, data preprocessing and statistical analyses were performed to determine how ecological safety (danger, predation, exposure) and physical traits (body weight, brain weight, gestation time) impact daily sleep patterns[cite: 1].

## Key Pipeline Steps
* **Data Cleaning & Normalization**: Replaced non-numeric placeholder characters (e.g., `?`) with `NaN` across missing values (`total_sleep`, `gestation_time`, `max_life_span`)[cite: 1].
* **Type Casting & Filtering**: Coerced features into floating-point and integer types, removing incomplete rows to yield a clean dataset of **58 complete animal observations** (`sleep_analysis1`)[cite: 1].
* **Statistical Analysis**: Calculated summary statistics and a Pearson correlation matrix to evaluate features influencing total sleep hours[cite: 1].

## Summary Statistics (`N = 58`)
* **Total Sleep**: Mean = **10.53 hrs/day** (Min: 2.60, Max: 19.90, Std: 4.61)
* **Gestation Time**: Mean = **136.03 days** (Min: 12.00, Max: 645.00)
* **Body Weight**: Mean = **198.40 kg** (Min: 0.005, Max: 6654.00)
* **Danger Index (1–5 scale)**: Mean = **2.53** (Min: 1.00, Max: 5.00)

## Correlation Key Takeaways
| Feature Pair | Pearson Correlation ($r$) | Interpretation |
| :--- | :--- | :--- |
| **Total Sleep vs. Sleep Exposure Index** | `-0.642` | Strongest negative driver; higher sleep exposure leads to less sleep. |
| **Total Sleep vs. Gestation Time** | `-0.631` | Species with longer developmental cycles sleep significantly less. |
| **Total Sleep vs. Danger Index** | `-0.588` | Overall environment danger reduces daily sleep duration. |
| **Body Weight vs. Brain Weight** | `0.934` | Extremely strong positive biological scaling relationship. |
| **Predation Index vs. Danger Index** | `0.928` | Predation threat is the primary component of overall species danger. |

## Core Finding
Environmental threat and exposure are the main negative predictors of daily sleep in mammals—animals at higher risk of predation or exposed while sleeping spend far fewer hours asleep per day.
