# 🚚 Asset Utilization Project

![Status](https://img.shields.io/badge/status-active-brightgreen)
![Python](https://img.shields.io/badge/python-3.8+-blue)

An exploratory data science project analyzing asset utilization patterns in an unlabeled asset dataset. The goal is to assess long-term performance and cost impact when high-usage assets are retained beyond their typical lifecycle.

> ⚠️ All data in this repository is randomly generated and anonymized. The methods and insights, however, are applicable to many operational assets across various industries.

---

## 📚 Table of Contents

- [Overview](#-overview)
- [Project Goals](#-project-goals)
- [Project Steps](#-project-steps)
- [Installation](#-installation)
- [Usage](#-usage)
- [Example](#-example)
- [Notebooks](#-notebooks-included)


---

## 📌 Overview

Many operational assets serve multiple usage roles. For this study, we consider two general task types:

- **Task A**: High-usage operations typically requiring newer, more reliable assets.
- **Task B**: Lower-usage operations, often assigned to older or less critical units.

This project analyzes a group of assets with **no explicit labeling** of asset roles. The aim is to use clustering and predictive modeling to infer operational patterns and assess the impact of **not retiring high-usage units**, even when exceeding the typical usage threshold of **750,000**.

> Assets operating beyond this threshold tend to incur significantly higher maintenance costs, which will be modeled in the final analysis.

---

## 🎯 Project Goals

- Automatically infer asset roles using unsupervised learning
- Forecast next-year usage by task type
- Quantify cost implications of exceeding standard usage thresholds
- Provide a reusable and scalable analysis pipeline

---

## 🧪 Project Steps

1. **Data Cleaning**  
   Prepare and validate raw asset usage data.

2. **Role Inference**  
   Apply **K-Means Clustering** to classify assets into Task A and Task B based on behavioral patterns.

3. **Segmentation**  
   Organize assets into operational role groups for analysis.

4. **Forecasting (Task A)**  
   Use **Linear Regression** to estimate future mileage for Task A assets, which typically follow consistent usage trends.

5. **Forecasting (Task B)**  
   Use **median-based projection** for Task B assets, reflecting more variable and less predictable usage.

6. **Cost Analysis**  
   Identify assets exceeding 750k miles and estimate increased maintenance costs.

---

## 💻 Installation

```bash
git clone https://github.com/yourusername/asset-utilization-project.git
cd asset-utilization-project
pip install -r requirements.txt

## ▶️ Usage
Run the full analysis using the included Jupyter Notebooks:

jupyter notebook initial_analysis.ipynb
jupyter notebook asset_utilization_model.ipynb


##🧾 Example

from sklearn.cluster import KMeans
import pandas as pd

# Load and clean data
df = pd.read_csv("asset_data.csv")
clean_df = preprocess_data(df)

# Apply KMeans clustering to infer task types
kmeans = KMeans(n_clusters=2)
df["Cluster"] = kmeans.fit_predict(clean_df[["AvgMonthlyMileage"]])

# Map clusters to generalized task types
df["TaskType"] = df["Cluster"].map({0: "Task A", 1: "Task B"})

##📂 Notebooks Included
initial_analysis.ipynb: Full EDA, clustering, forecasting, and cost modeling.
asset_utilization_model.ipynb: Condensed and reusable version for ongoing evaluations.
