# Political Alignments and Civil Society: Examining NGO Influence on Electoral Patterns in Istanbul's Neighborhoods

**Author**: Mehmet Boran Göksel

---

## Introduction

In recent years, studies on non-governmental organizations (NGOs) in Turkey have increased. While many continue to operate with the goal of delivering social benefits, a growing portion have been observed making statements in support of the government and engaging in politically aligned activities. It is also known that political figures—including children of AK Party leaders—are often involved in founding or supporting these organizations.

This shift signals a potential redefinition of NGOs in Turkey, from traditionally independent entities to politically aligned instruments. This evolving role raises questions about both the influence of political actors on NGOs and the reciprocal impact of NGOs on electoral outcomes.

The AK Party has long been criticized for using social assistance as a vote-gathering tool—a critique embodied in the nickname "pasta party." Recent scandals and publicized instances of favoritism have further fueled these criticisms.

---

## Literature Review

Despite its significance, the relationship between the AK Party and NGOs has received limited scholarly attention. NGOs are vital components of a healthy democracy and are ideally meant to operate independently from the state.

The Bureau of International Information Programs notes:

> "NGOs should operate under minimal political control of states."

When this principle is violated, NGOs risk becoming tools of implicit political campaigning. Köse (2019) introduces the concept of **Indirect Political Patronage (IPP)** to describe the role of religious NGOs that consolidate government influence in Turkey. These NGOs act as intermediaries between the state and the public, often lacking transparency and autonomy.

---

## Methodology

### Data Acquisition

#### NGOs Dataset

- **Source**: General Directorate of Relations with Civil Society
- **Method**: Used browser inspection and API calls via INSOMNIA to access NGO data (approx. 101,000 entries, with 23,119 from Istanbul).
- **Processing**: Data parsed using a Python script and geocoded via Google Geocoding API. Results were categorized by province, district, and neighborhood.

#### 2023 General Elections Dataset

- **Source**: Supreme Election Council
- **Method**: Manually compiled from ballot box-level results, aggregated to neighborhood-level data.

### Data Cleaning

- **Polygon Data**: GeoJSON neighborhood data from Izzetkalic’s GitHub repo.
- **Tool**: QGIS for spatial joins.
- **Challenge**: Discrepancies in neighborhood names.
- **Solution**: Fuzzy matching with `fuzzywuzzy` Python library followed by manual review.

---

## Data Analysis

### Visualizations

1. **AK Party Vote Share Map**  
   Displays neighborhood-level support for the AK Party in 2023, with darker shades indicating higher vote percentages.

2. **NGO Distribution Map**  
   Shows concentrations of NGOs. Two main clusters appear:
   - Bağcılar, Esenler, Başakşehir, and Fatih
   - Kadıköy, Ataşehir, Maltepe, and Üsküdar  
   Other areas show relatively sparse NGO presence.

### Linear Regression

Objective: Assess whether the presence of different types of NGOs predicts AK Party vote share.

- **Model**: Ordinary Least Squares (OLS)
- **Dependent Variable**: AK Party vote percentage
- **Independent Variables**: Counts of 21 NGO categories
- **Sample Size**: 869 neighborhoods with NGO presence

#### Key Findings

- **R-squared**: 0.247 — the model explains about 24.7% of the variance.
- **Statistically Significant Predictors**:
  - *Religious NGOs* and *Educational NGOs* show a **positive** impact.
  - *Environmental* and *Thought-Based NGOs* show a **negative** correlation.
- **Model Validity**:
  - F-statistic = 13.25 (p < 0.001)
  - Residuals are independent and normally distributed.

These results suggest that NGO activity is not politically neutral, and some types of NGOs correlate strongly with political preferences.

---

## Conclusion

This study explores the increasing political entanglement of NGOs in Turkey, particularly their alignment with the AK Party. The regression analysis shows that NGO presence—especially in religious and educational sectors—correlates with stronger support for the ruling party.

The findings highlight:
- The emergence of **Indirect Political Patronage**
- The influence of **NGO types** on **electoral patterns**
- The **erosion of NGO autonomy**, raising concerns about democratic health

---

---

## Licensing

This repository is shared for **academic and non-commercial research purposes**. You are **free to use, modify, and build upon** this work, provided that you **credit the original author**, Mehmet Boran Göksel.

Please include a citation or link to this repository in any derivative works, publications, or presentations.

---

Let me know if you'd like a downloadable PDF version or a specific citation format (APA, MLA, etc.) to include as well.
