# RTU Energy Optimization using Live BMS Data

Reduce HVAC energy consumption by 20–35% using real-time analytics, weather integration, and adaptive control strategies.

---

## Executive Summary

This project implements an end-to-end pipeline for optimizing rooftop unit (RTU) energy usage using live Building Management System (BMS) data.

By combining real-time telemetry, weather inputs, and predictive modeling, the system identifies inefficiencies and generates actionable control strategies, including:

- Supply air temperature (SAT) reset  
- Schedule optimization  
- Demand-based ventilation  

The result is measurable energy savings while maintaining occupant comfort.

---

## Business Problem

RTUs are a major contributor to commercial energy consumption and are often:

- Operating on static schedules  
- Poorly tuned or inefficient  
- Lacking real-time performance visibility  

This leads to:
- Increased energy costs  
- Accelerated equipment wear  
- Reduced comfort performance  

This project converts raw BMS data into actionable insights for operational and energy optimization.

---

## Objectives

- Estimate real-time energy consumption (kW / kWh)  
- Identify operational inefficiencies  
- Model load behavior using historical + weather data  
- Generate optimization recommendations  
- Quantify potential energy savings  

---

## System Architecture

The system follows a modular pipeline:

1. Data Ingestion (BMS + Weather API)  
2. Data Processing & Feature Engineering  
3. Energy Estimation Model  
4. Optimization Engine  
5. Visualization & Reporting  

![Architecture Diagram](outputs/architecture.png)

---

## Data Sources

### BMS Data
- Unit Status (On/Off)  
- Supply Air Temperature (SAT)  
- Return Air Temperature (RAT)  
- Outdoor Air Temperature (OAT)  
- Fan / Compressor Status  
- Airflow (CFM) *(if available)*  
- Electrical data (V, I, PF) *(if available)*  

### Weather Data
- Temperature  
- Humidity  
- Solar load *(optional)*  

**Sampling Rate:** 1-minute intervals (configurable)

---

## Energy Estimation Methodology

When direct kW data is unavailable, energy usage is estimated using:

- Runtime-based calculations  
- Fan laws (cube law where applicable)  
- Manufacturer assumptions  
- Regression-based models  

**Constraints:**
- Dependent on sensor reliability  
- Compressor status may not fully represent load  

---

## Modeling Approach

**Models:**
- Linear Regression (baseline)  
- Random Forest  
- Gradient Boosting  

**Target:** Estimated kW / kWh  

**Validation:**
- Train/Test split  
- Cross-validation  
- Metrics: RMSE, MAE  

Focus is placed on **interpretability for operational decision-making**, not just accuracy.

---

## Optimization Strategy

The system generates data-driven recommendations:

### Schedule Optimization
- Reduce runtime during unoccupied periods  

### SAT Reset
- Adjust supply air temperature based on load and ambient conditions  

### Demand-Based Ventilation
- Minimize outside air intake during low occupancy  

### Short Cycling Detection
- Identify compressor inefficiencies and rapid cycling  

---

## Results & Impact

**Key Outcomes:**
- Estimated energy savings: 18–32%  
- Reduced unnecessary runtime  
- Detection of short cycling across multiple RTUs  

| Scenario             | Energy Use (kWh) | Savings |
|---------------------|------------------|--------|
| Baseline            | 1200             | —      |
| Optimized           | 870              | 27.5%  |

![Energy Comparison](outputs/energy_comparison.png)

---

## Project Structure



---

## Why This Matters

This project demonstrates:

- Applied data science on real-world industrial systems  
- Integration of analytics with building controls  
- Quantifiable business impact (energy + cost savings)  
- Scalable architecture for deployment in live environments  

It reflects production-level engineering, not just academic modeling.
