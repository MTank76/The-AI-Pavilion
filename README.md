# The-AI-Pavilion: Project Documentation

This repository contains a comprehensive machine learning framework designed to predict the winner of the IPL 2026 season. By leveraging historical match data (2008–2025), squad strengths, and real-time form, this application provides high-accuracy win probability analysis and match simulations.

---

## 🚀 Business Use Case: Predictive Sports Analytics

The primary goal of this project is to assist sports analysts, team owners, and fans in making data-driven decisions. Beyond simple "win/loss" predictions, the application quantifies the impact of variables like toss outcomes, venue advantage, and player availability.

**Wider Industry Applications:**
The logic used in this project can be adapted for several high-value business sectors:
* **Retail & Demand Forecasting:** Replacing "teams" with "products" and "match conditions" with "seasonal trends" to predict inventory sell-through rates.
* **Finance/Stock Market:** Using ensemble models to predict asset price movements based on historical volatility and external market triggers.
* **Customer Churn Prediction:** Analyzing "player availability" and "recent form" logic to identify which customers are likely to leave a service based on their recent interaction patterns.
* **Logistics:** Predicting supply chain bottlenecks by analyzing "Venue Advantage" (Node capacity) and "Squad Strength" (Resource availability).

---

## 🛠️ The Approach & Methodology

The problem was approached as a **Multi-Class Classification and Probability Estimation** challenge. The workflow followed these key phases:

1.  **Data Acquisition & Cleaning:** Historical IPL data from 2008 to 2025 was processed. Feature engineering was used to create metrics like `Recent Team Form`, `Head-to-Head Win Rate`, and `Venue Bias`.
2.  **Feature Importance:** Using tree-based models, I identified that **Squad Strength** and **Recent Team Form** are the highest predictors of a win, followed by Venue Advantage and Toss Outcome.
3.  **Model Ensemble:** Instead of relying on a single algorithm, I implemented a variety of models to ensure robustness, ultimately using an **Ensemble Meta-Classifier** to combine the strengths of individual learners.
4.  **Deployment:** The entire engine is wrapped in a **Streamlit** web application, providing an interactive dashboard for real-time simulations and historical trend analysis.

---

## 📊 Model Performance & Comparison

The project evaluates several sophisticated algorithms to find the best fit for the volatile nature of T20 cricket.

| Model | CV Accuracy (%) | Test Accuracy (%) | Reliability (AUC) |
| :--- | :--- | :--- | :--- |
| **Random Forest** | 63.5% | 67.1% | 0.70 |
| **XGBoost** | 63.0% | 64.0% | 0.71 |
| **LightGBM** | 64.8% | 66.0% | 0.71 |
| **Extra Trees** | 64.4% | 65.1% | 0.69 |
| **Neural Network** | 60.8% | 60.5% | 0.61 |
| **Ensemble (Final)** | N/A | **64.2%** | **0.71** |

### Key Findings:
* **LightGBM** showed the highest Cross-Validation accuracy, making it excellent for handling categorical team data.
* The **Ensemble Model** provides the most reliable AUC score (0.71), balancing bias and variance across different match conditions.
* **Squad Strength** accounts for over 40% of the prediction weight, highlighting that team composition is the most critical factor in modern IPL seasons.

> **Key Insight:** Feature Importance analysis reveals that **Squad Strength** accounts for \~42% of the prediction weight, followed by **Venue Advantage** (18%).

[](https://www.python.org/)
[](https://the-ai-pavilion-ipl.streamlit.app/)
[](https://www.google.com/search?q=https://github.com/MTank76/The-AI-Pavilion)

-----

## 🖥️ Feature Highlights

### 📍 Match Simulator

An interactive sandbox where you can toggle teams, venues, and toss winners. The model updates the win probability in real-time, providing a "Pre-Match Odds" profile.

### 📈 Historical Dynasty Tracking

A deep dive into franchise performance cycles. Visualize how teams like MI and CSK maintained dominance and identify the "rebuilding phases" of emerging teams.

### 🏆 2026 Forecast

Currently, based on 2025 squad retention and form metrics, the model identifies **Royal Challengers Bengaluru (RCB)** and **Rajasthan Royals (RR)** as the primary contenders for the 2026 title.

-----

## ⚙️ Installation & Local Setup

**1. Clone the environment**

```bash
git clone https://github.com/MTank76/The-AI-Pavilion.git
cd The-AI-Pavilion
```

**2. Setup Virtual Environment**

```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

**3. Install Dependencies**

```bash
pip install -r requirements.txt
```

**4. Fire up the Dashboard**

```bash
streamlit run app.py
```

-----

## 📂 Project Structure

```text
├── data/               # Historical IPL Datasets (2008-2025)
├── models/             # Saved Ensemble & Individual Pickles
├── notebooks/          # EDA & Model Training Scripts
├── src/                # Modular Python logic for Feature Engineering
├── app.py              # Streamlit UI & Logic
└── requirements.txt    # Dependency Manifest
```
## 🧪 Technologies Used
* **Language:** Python
* **Libraries:** Pandas, Scikit-learn, XGBoost, LightGBM, Plotly
* **Frontend:** Streamlit
* **Version Control:** Git

-----


