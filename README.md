# 🚛 Tractor Utilization Project

![Status](https://img.shields.io/badge/status-active-brightgreen)
![License](https://img.shields.io/badge/license-MIT-blue)
![Python](https://img.shields.io/badge/python-3.8+-blue)

An exploratory data science project analyzing tractor (semi-truck) utilization in a transportation fleet. The goal is to assess performance and long-term cost impact if no tractors are replaced, even after exceeding standard mileage limits.

> ⚠️ All data in this repository is randomly generated and anonymized for privacy. However, the methods and insights are applicable to real-world fleets.

---

## 📚 Table of Contents

- [Overview](#-overview)
- [Project Goals](#-project-goals)
- [Project Steps](#-project-steps)
- [Installation](#-installation)
- [Usage](#-usage)
- [Example](#-example)
- [Notebooks](#-notebooks-included)
- [License](#-license)

---

## 📌 Overview

Tractors in commercial fleets typically serve two functions:

- **Line Haul**: Long-distance freight between hubs. Assigned to newer tractors due to reliability and fuel efficiency.
- **Pickup & Delivery (P&D)**: Local deliveries. Assigned to older tractors due to shorter, lower-mileage routes.

This project examines a fleet where roles are **not** explicitly labeled. We'll use data-driven techniques to infer usage roles and predict operational impacts when **tractors over 750,000 miles are not retired**.

---

## 🎯 Project Goals

- Automatically classify tractor roles using unsupervised learning
- Forecast annual mileage growth
- Estimate increased maintenance cost for high-mileage tractors
- Build a reusable Python analysis pipeline

---

## 🧪 Project Steps

1. **Data Cleaning**  
   Prepare and organize raw input data.

2. **Classification**  
   Use **K-Means Clustering** to identify Line Haul vs. P&D units.

3. **Segmentation**  
   Group tractors into Line Haul and P&D categories.

4. **Forecasting (Line Haul)**  
   Apply **Linear Regression** to estimate next year’s mileage.

5. **Forecasting (P&D)**  
   Use **median** mileage to estimate next year’s usage.

6. **Cost Calculation**  
   Determine how many tractors exceed 750k miles and estimate added maintenance costs.

---

## 💻 Installation

```bash
git clone https://github.com/tcaparatta/tractor-utilization-project.git
cd tractor-utilization-project
pip install -r requirements.txt
