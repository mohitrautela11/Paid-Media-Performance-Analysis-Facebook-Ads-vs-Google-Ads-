# 📊 A/B Testing & Regression Analysis — Facebook Ads vs Google AdWords

> **Data-driven evaluation of digital advertising performance to support marketing budget allocation and campaign optimization.**

## 📌 Project Overview

Digital marketing teams need to continuously evaluate whether their advertising spend is generating meaningful business outcomes.

This project analyzes **365 days of advertising data from 2019** to compare the performance of **Facebook Ads and Google AdWords** across conversions, clicks, costs, and conversion efficiency.

Rather than relying only on descriptive metrics, I used **statistical hypothesis testing, correlation analysis, regression modeling, and time-based analysis** to determine whether the observed performance differences were meaningful and how advertising activity could influence conversions.

The project was designed around a practical business question:

> **If a company has to decide where to prioritize its digital advertising budget, which platform provides stronger conversion performance and what factors should influence that decision?**

---

## 🎯 Business Problem

A digital marketing agency is managing advertising campaigns across:

- Facebook Ads
- Google AdWords

Both platforms generated substantial traffic and advertising spend throughout 2019. However, higher clicks or higher spend do not automatically mean better business performance.

The business needed to understand:

1. Which platform generates more conversions?
2. Is the difference in conversion performance statistically significant?
3. Does increasing clicks translate into more conversions?
4. How can expected conversions be estimated from advertising clicks?
5. When does advertising performance vary throughout the year?
6. What does the relationship between advertising cost and conversions indicate for future budget planning?

---

# 🔍 Analytical Approach

The project followed a business-oriented analytical workflow:

```text
Raw Campaign Data
       ↓
Data Loading & Preparation
       ↓
Exploratory Data Analysis
       ↓
Facebook vs Google Ads Comparison
       ↓
Click → Conversion Relationship
       ↓
A/B / Hypothesis Testing
       ↓
Regression Analysis
       ↓
Time-Based Performance Analysis
       ↓
Cost & Conversion Relationship
       ↓
Business Recommendations
```

---

# 📂 Dataset

The dataset contains **365 daily observations** covering the 2019 advertising campaigns.

### Key metrics

| Category | Metrics |
|---|---|
| Reach | Ad Views / Impressions |
| Engagement | Clicks |
| Outcome | Conversions |
| Spend | Advertising Cost |
| Efficiency | CTR, Conversion Rate, CPC |
| Time | Daily Date |

Both Facebook and Google AdWords have comparable performance metrics, allowing direct campaign-level analysis.

---

# 🛠️ Tools & Technologies

### Programming & Analysis
- **Python**
- **Pandas**
- **NumPy**

### Statistical Analysis
- **SciPy**
- Independent two-sample **t-test**
- Correlation analysis
- Cointegration analysis

### Machine Learning / Predictive Analysis
- **Scikit-learn**
- Linear Regression
- R²
- Mean Squared Error

### Visualization
- **Matplotlib**
- **Seaborn**

### Environment
- Jupyter Notebook

---

# 📊 Key Analysis & Findings

## 1. Facebook vs Google AdWords Performance

The first step was to compare the overall campaign performance.

### Average daily performance

| Metric | Facebook | Google AdWords |
|---|---:|---:|
| Clicks | 83.06 | 264.08 |
| Conversions | 2.00 | 11.18 |
| Cost | 2,685.20 | 15,118.06 |

Across the year:

- **Facebook generated 731 conversions**
- **Google AdWords generated 4,079 conversions**
- AdWords generated substantially more clicks and conversions.

This established AdWords as the stronger platform in terms of **absolute conversion volume**.

However, raw conversion volume alone was not considered sufficient to make a budget-allocation decision.

---

# 🧪 2. Statistical Hypothesis Testing

To determine whether the conversion difference between the two platforms was statistically meaningful, I performed an independent two-sample t-test.

### Hypothesis

**H₀:** There is no meaningful difference in conversion performance between Facebook and AdWords.

**H₁:** AdWords generates more conversions than Facebook.

### Result

```text
T-statistic: -34.41
p-value:     1.48 × 10⁻¹²¹
```

The p-value is far below the **0.05 significance level**.

### Conclusion

The observed difference in conversion performance is **statistically significant**.

This provides stronger evidence for prioritizing AdWords based on conversion volume rather than treating the difference as random variation.

---

# 📈 3. Does More Engagement Lead to More Conversions?

A key marketing question was whether additional ad clicks were associated with additional conversions.

Correlation analysis showed a strong positive relationship:

| Platform | Click → Conversion Correlation |
|---|---:|
| Facebook | **0.859** |
| Google AdWords | **0.873** |

Both platforms showed a strong positive relationship between clicks and conversions.

### Business Interpretation

Increasing qualified traffic can contribute to higher conversion volume.

However, correlation does **not** prove causation. Therefore, I used regression analysis to further quantify the relationship for AdWords.

---

# 🤖 4. Regression Analysis — Predicting AdWords Conversions

I built a simple linear regression model using:

**Input:** AdWords Clicks  
**Target:** AdWords Conversions

### Model performance

```text
R² Score: 76.13%
MSE:      5.89
```

The model explains approximately **76% of the variation in daily AdWords conversions** using clicks as the predictor.

### Example predictions

| AdWords Clicks | Expected Conversions |
|---:|---:|
| 50 | ~1.98 |
| 80 | ~3.27 |

### Business Value

This creates a simple planning framework for marketers:

```text
Expected Click Volume
        ↓
Regression Model
        ↓
Expected Conversions
        ↓
Campaign Planning
        ↓
Budget & Performance Decisions
```

The model is not intended to replace campaign forecasting systems, but it demonstrates how historical advertising data can be converted into a **quantifiable planning input**.

---

# 📅 5. Time-Based Campaign Analysis

The project also analyzed AdWords performance across:

- Days of the week
- Months
- Monthly conversion volume
- Monthly cost per conversion

This helps identify periods where campaign performance changes and provides a basis for investigating:

- seasonal demand
- campaign timing
- budget allocation
- changes in customer behavior

Rather than treating the entire year as one homogeneous period, the analysis considers **when advertising performance occurs**.

---

# 💰 6. Cost & Conversion Analysis

Advertising spend was analyzed alongside conversions to understand whether cost and conversion performance move together over time.

The analysis produced a highly significant cointegration result:

```text
Cointegration p-value:
3.74 × 10⁻¹⁹
```

The result indicates a statistically significant long-term relationship between AdWords advertising cost and conversions in this dataset.

### Business Interpretation

Advertising investment and conversion output demonstrate a stable long-term relationship in the observed data.

This supports using historical cost and conversion trends when evaluating future advertising investment, while still considering factors such as campaign quality, audience targeting and conversion economics.

---

# 💡 Business Recommendations

Based on the analysis, several practical recommendations emerge.

### 1. Prioritize AdWords for conversion-focused campaigns

AdWords produced significantly higher conversion volume than Facebook in the analyzed dataset.

For campaigns where the primary objective is **conversion generation**, AdWords should receive stronger consideration in budget allocation.

### 2. Monitor clicks as an important performance indicator

Both platforms showed strong positive relationships between clicks and conversions.

However, marketers should optimize for **qualified clicks and conversions**, rather than maximizing traffic alone.

### 3. Use predictive analysis for campaign planning

The regression model provides a simple way to estimate expected conversions from planned click volumes.

This can support:

- campaign forecasting
- target setting
- budget planning
- performance benchmarking

### 4. Analyze performance by time period

Campaign performance should not be evaluated only using annual averages.

Monthly and weekly analysis can help identify opportunities for:

- budget reallocation
- campaign timing
- seasonal optimization
- performance investigation

### 5. Combine statistical evidence with marketing metrics

A platform should not be selected purely because it has more clicks or conversions.

A stronger decision framework combines:

```text
Volume
+
Conversion Performance
+
Cost
+
Statistical Significance
+
Time Trends
=
Better Marketing Decision
```

---

# 👨‍💻 What I Built

This project demonstrates an end-to-end marketing analytics workflow:

### Data Analyst Perspective

- Loaded and explored campaign-level data using Pandas
- Performed descriptive statistical analysis
- Investigated distributions and potential outliers
- Calculated correlations
- Conducted statistical hypothesis testing
- Built a linear regression model
- Evaluated model performance using R² and MSE
- Performed time-based analysis
- Applied cointegration analysis
- Translated statistical findings into business recommendations

### Marketing Analyst Perspective

- Compared advertising channel performance
- Evaluated click and conversion behavior
- Assessed campaign efficiency
- Investigated cost vs conversion relationships
- Identified the stronger conversion channel
- Used data to support advertising budget decisions
- Applied predictive analysis to campaign planning
- Connected marketing KPIs with business outcomes

---

# 📌 Key Takeaways

The analysis demonstrates that:

> **Google AdWords significantly outperformed Facebook in conversion volume within the analyzed 2019 dataset, and the difference was statistically significant.**

At the same time, both platforms showed strong positive relationships between clicks and conversions, indicating that engagement can be an important leading indicator of conversion activity.

The regression model further showed that **AdWords clicks could explain approximately 76% of the variation in daily conversions**, providing a useful starting point for conversion forecasting.

The overall project demonstrates how marketing data can move from **raw campaign metrics → statistical evidence → predictive analysis → actionable business decisions.**

---

# 🚀 Skills Demonstrated

`Python` `Pandas` `NumPy` `SciPy` `Scikit-learn` `Matplotlib` `Seaborn` `Jupyter Notebook`

`A/B Testing` `Hypothesis Testing` `Statistical Analysis` `Regression Analysis` `Correlation Analysis`

`Marketing Analytics` `Campaign Analysis` `Digital Marketing` `Performance Marketing`

`Data Visualization` `Business Analysis` `Conversion Analysis` `Marketing ROI` `Decision Making`

---

# 📁 Project Structure

```text
AB-Testing-Marketing-Analytics/
│
├── AB_testing.ipynb
├── marketing_campaign_2019.csv
└── README.md
```

---

