# Aviation-Customer-Satisfaction-Delay-Analysis
SkyBound Analytics partners with several leading airlines to enhance operational efficiency and customer experience using data science. Airline customers often face service delays, inconsistent satisfaction levels, and unreliable loyalty experiences. In this project, we explore flight-level data to uncover actionable patterns that inform delay reduction and passenger satisfaction strategies.


# Aviation Customer Satisfaction & Delay Analysis

## Case Study: Driving Satisfaction Through Data for SkyBound Airlines

**Tools Used:** Python, Pandas, Seaborn, Matplotlib, Jupyter Notebook\
**Dataset:** 5,050 observations from 5 airlines including delays, satisfaction, loyalty, etc.

---

### Business Overview

SkyBound Analytics partners with several leading airlines to enhance operational efficiency and customer experience using data science. Airline customers often face service delays, inconsistent satisfaction levels, and unreliable loyalty experiences. In this project, we explore flight-level data to uncover actionable patterns that inform delay reduction and passenger satisfaction strategies.

---

### Problem Statement

Airlines are challenged by:

- Frequent **flight delays** impacting satisfaction and efficiency
- Inconsistent loyalty experiences across service classes
- Lack of visibility into what influences **customer sentiment**
- Underused operational data that could drive improvements

---

### Project Objectives

- Identify the key drivers of **customer satisfaction**
- Uncover factors influencing **delays and inefficiencies**
- Quantify relationships between **service classes**, **loyalty programs**, and **performance**
- Provide insights to improve **operations and experience** using Python EDA

---

###  Methodology

This project was conducted using a **Python-based exploratory data analysis (EDA)** process:

1. **Data Import & Cleaning:**

   - Handled missing values (notably satisfaction)
   - Converted timestamps to datetime
   - Removed duplicates

2. **Feature Engineering:**

   - Created `DelayRate = DelayMinutes / FlightDuration`
   - Categorized delay levels (None, Minor, Major)

3. **Visual Analysis & Insights:**

   - Used boxplots, histograms, and correlation heatmaps to find trends
   - Compared satisfaction across airlines, classes, loyalty membership, maintenance events

---

###  Key Insights

| Insight                                                          | Impact                                              |
| ---------------------------------------------------------------- | --------------------------------------------------- |
| **Only 26% of flights arrive on schedule**                       | Operational inefficiencies are widespread           |
| **Satisfaction drops from \~7.1 to \~4.6 when delays > 60 mins** | Delays significantly affect perception              |
| **First-class & loyalty customers report higher satisfaction**   | Premium service boosts sentiment                    |
| **Maintenance incidents lower satisfaction by \~2 points**       | Reliability matters greatly                         |
| **Weather had little measurable effect**                         | Internal operations may matter more than conditions |

---

###  Business Recommendations

- **Prioritize aircraft maintenance:** Preventive action can reduce disruptions
- **Improve delay handling:** Communicate & streamline turnaround processes
- **Strengthen loyalty benefits:** Continue rewarding premium and returning passengers
- **Optimize for peak travel seasons:** Use demand planning and resource allocation

---

###  Technical Walkthrough

#### Libraries Used

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
```

#### Data Preparation

```python
df = pd.read_csv('aviation_dataset.csv')
df['Date'] = pd.to_datetime(df['Date'])
df.dropna(subset=['CustomerSatisfaction'], inplace=True)
df['DelayRate'] = df['DelayMinutes'] / df['FlightDuration']
```

#### Visualizations

```python
sns.boxplot(x='FlightClass', y='CustomerSatisfaction', data=df)
plt.title('Customer Satisfaction by Flight Class')
plt.show()
```

```python
sns.heatmap(df.corr(), annot=True, cmap='coolwarm')
plt.title('Correlation Matrix')
plt.show()
```

---

###  Conclusion

This project demonstrates how **Python EDA** techniques can transform aviation data into strategic insight. The structured approach taken helped identify clear pain points (delays, service inconsistency) and success levers (loyalty, premium class). My analysis bridges technical depth with practical storytelling for decision-makers in aviation.

## Files in this Repository

-   `Aviation Customer Satisfaction and Delay Analysis.ipynb`: The main Jupyter Notebook containing all the code for data loading, cleaning, EDA, feature engineering, and insights generation.
-   `aviation_dataset.xlsx`: The raw dataset used for the project. 
-   `README.md`: This file.
