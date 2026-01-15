
## 🚦 TTI Smart Corridor Digital Twin## AI-Enhanced Traffic Operations Platform

**Author:** Rob Cushard  
**Status:** Proof of Concept (PoC) for Texas A&M Transportation Institute Strategic Review

---

## 📋 Executive Summary
This application is a **Digital Twin** platform designed to transition traffic signal management from static, compliant-based timing plans to **dynamic, risk-aware operations**. 

It integrates **Discrete Event Simulation (DES)** with **Generative AI** to audit signal corridors not just for theoretical physics, but for "Human Factors" (distracted driving, reaction latency, and stochastic demand).

## 🚀 Key Features

### 1. Physics-Based Simulation Engine (`SimPy`)
* **Car-Following Logic:** Models the "Snake Effect" where queue dissipation is limited by the reaction time of the driver ahead.
* **Platoon Dispersion:** Simulates how speed variance breaks the "Green Wave" between intersections.
* **Stochastic Demand:** Uses exponential distribution for vehicle arrivals to model real-world "clumpiness" rather than smooth averages.

### 2. Monte Carlo Risk Engine
* **Statistical Significance:** Instead of a single run, the engine executes **30+ parallel iterations** of rush hour scenarios.
* **Risk Profiling:** Generates a probability distribution of Wait Times, allowing engineers to see the "Long Tail" risks (Level of Service F events).
* **Audit Matrix:** Automatically flags specific simulation runs that exceeded failure thresholds using a heat-map visualizer.

### 3. Generative AI Auditor (`Google Gemini 1.5 Flash`)
* **Automated Insights:** An AI Agent acts as a "Virtual Director," analyzing the raw simulation data to provide plain-English executive summaries.
* **Operational Recommendations:** The AI detects patterns (e.g., instability due to high reaction times) and suggests specific interventions (retiming vs. demand metering).

---

## 🛠️ Installation & Usage

### Prerequisites
* Python 3.8+
* A Google Gemini API Key (Optional, for AI features)

### Quick Start
```bash
# 1. Clone the repository
git clone [https://github.com/robcushard-nth/traffic.git](https://github.com/robcushard-nth/traffic.git)

# 2. Navigate to the directory
cd traffic

# 3. Install dependencies
pip install -r requirements.txt

# 4. Launch the Dashboard
streamlit run app_traffic_twin.py