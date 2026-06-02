# Supplementary Materials for Power-System-Oriented Extreme Weather Scenario Identification

This repository provides supplementary figures, aggregated statistics, and documentation for the manuscript:

**Power-System-Oriented Extreme Weather Scenario Identification: Hybrid Classical–Quantum Learning for Minority-Class Augmentation and Real-Sample Classification**

The purpose of this repository is to improve the transparency of the case study while protecting confidential power-grid operation data.

---

## 1. Data Availability Statement

The original dataset used in this study was collected from a real provincial power grid. Due to data confidentiality, privacy restrictions, and grid-operation security concerns, the raw data cannot be publicly released.

To improve transparency and reproducibility, this repository provides distribution-level and aggregated information, including:

- class-wise sample counts;
- train/validation/test split statistics;
- feature-level summary statistics;
- generated-sample statistics;
- distribution plots of meteorological and power-system variables;
- real-versus-generated sample comparisons;
- power-system risk-indicator distributions.

No raw load curves, original timestamps, equipment-level records, dispatch records, grid topology information, device names, geographical coordinates, or identifiable operation data are included.

---

## 2. Repository Scope

This repository is intended as an online supplementary material rather than a public raw-data release.

It provides:

1. aggregated statistics of the real-world dataset;
2. anonymized distribution-level visualization figures;
3. summary information about labeled extreme-weather scenarios;
4. summary information about generated minority-class samples;
5. risk-indicator distributions used to support the power-system-oriented interpretation of the identified scenarios.

The generated samples are used only for training-set augmentation in the manuscript. The validation and test sets consist only of real observed samples.

---

## 3. Scenario Classes

The considered scenario classes include:

| Category | Event class | Power-system-oriented interpretation |
|---|---|---|
| Normal condition | Normal | Regular meteorological and operating condition |
| Environmental extreme weather | Extreme high temperature | Potential peak-load increase and source-load balance stress |
| Environmental extreme weather | Extreme low temperature | Potential load increase and operational stress |
| Environmental extreme weather | Heavy-precipitation condition | Potential renewable-output reduction and load/renewable imbalance |
| Disaster extreme weather | Typhoon-related condition | Potential equipment exposure, outage risk, and resilience degradation |
| Disaster extreme weather | Icing-related condition | Potential line icing, equipment stress, and outage risk |

---

## 4. Dataset Overview

The case study uses meteorological and power-system operation variables to identify power-system-oriented extreme weather scenarios.

The main types of variables include:

- load-related variables;
- temperature;
- wind-speed-related variables;
- solar-irradiance-related variables;
- power-system risk indicators derived from source-load balance analysis.

The detailed variable descriptions are provided in:

[`docs/variable_description.md`](docs/variable_description.md)

---

## 5. Class Distribution

The class distribution of the real observed samples is provided below.

![Class distribution](figures/fig_class_distribution.png)

The corresponding aggregated statistics are provided in:

[`tables/class_count_summary.csv`](tables/class_count_summary.csv)

---

## 6. Train/Validation/Test Split

The data split follows the principle that generated samples are only used for training-set augmentation.

The validation and test sets contain only real observed samples.

![Train validation test split](figures/fig_train_val_test_split.png)

The corresponding split summary is provided in:

[`tables/train_val_test_split_summary.csv`](tables/train_val_test_split_summary.csv)

---

## 7. Feature Distributions by Scenario Class

The following figure shows the distribution-level characteristics of meteorological and power-system variables under different scenario classes.

![Feature distribution by class](figures/fig_feature_distribution_by_class.png)

The corresponding feature-level summary statistics are provided in:

[`tables/feature_statistics_by_class.csv`](tables/feature_statistics_by_class.csv)

---

## 8. Generated Minority-Class Samples

The proposed generation module is used to augment scarce minority-class extreme-weather samples in the training set.

It is not used to generate validation or test samples.

![Generated sample count](figures/fig_generated_sample_count.png)

The corresponding generated-sample statistics are provided in:

[`tables/generated_sample_summary.csv`](tables/generated_sample_summary.csv)

---

## 9. Real-versus-Generated Distribution Comparison

The following figure compares the distribution-level characteristics of real and generated minority-class samples.

![Real vs generated distribution](figures/fig_real_vs_generated_distribution.png)

This comparison is intended to show whether the generated samples preserve the statistical characteristics of real minority-class extreme-weather scenarios at the aggregated distribution level.

---

## 10. Power-System Risk Indicator Distributions

To support the power-system-oriented interpretation of the labeled and generated scenarios, this repository provides aggregated distributions of risk-related indicators, such as:

- peak load;
- net load;
- net-load ramping;
- renewable-output variation;
- reserve requirement;
- source-load imbalance indicator.

![Risk indicator distribution](figures/fig_risk_indicator_distribution.png)

The corresponding risk-indicator statistics are provided in:

[`tables/risk_indicator_summary.csv`](tables/risk_indicator_summary.csv)

---

## 11. Labeling Protocol Summary

The labeling process combines meteorological abnormality, power-system response, external event evidence, and manual verification.

A scenario is labeled as a power-system-oriented extreme-weather scenario when meteorological abnormality is jointly supported by power-system response or external event evidence.

A summary of the labeling protocol is provided in:

[`docs/labeling_protocol_summary.md`](docs/labeling_protocol_summary.md)

---

## 12. Repository Structure

```text
extreme-weather-power-system-supplement/
│
├── README.md
│
├── figures/
│   ├── fig_class_distribution.png
│   ├── fig_train_val_test_split.png
│   ├── fig_feature_distribution_by_class.png
│   ├── fig_generated_sample_count.png
│   ├── fig_real_vs_generated_distribution.png
│   └── fig_risk_indicator_distribution.png
│
├── tables/
│   ├── class_count_summary.csv
│   ├── train_val_test_split_summary.csv
│   ├── feature_statistics_by_class.csv
│   ├── generated_sample_summary.csv
│   └── risk_indicator_summary.csv
│
├── docs/
│   ├── data_availability_statement.md
│   ├── labeling_protocol_summary.md
│   └── variable_description.md
│
└── scripts/
    └── plot_distribution_from_summary.py
