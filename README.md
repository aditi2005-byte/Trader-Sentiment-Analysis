<div align="center">
  <h1>📈 PrimeTrade Data Science Intern Project</h1>
  <p><strong>Uncovering the Mathematical Edge Between Market Sentiment and Trader Behavior</strong></p>
  
  [![Python](https://img.shields.io/badge/Python-3.9+-blue.svg)](https://www.python.org/downloads/)
  [![Pandas](https://img.shields.io/badge/Pandas-Data_Wrangling-150458.svg)](https://pandas.pydata.org/)
  [![XGBoost](https://img.shields.io/badge/scikit--learn-Machine_Learning-F7931E.svg)](https://scikit-learn.org/)
  [![Jupyter](https://img.shields.io/badge/Jupyter-Interactive_Analysis-F37626.svg)](https://jupyter.org/)
</div>

<br/>

## **Project Overview**
This project analyzes how market sentiment (Fear/Greed) influences trader behavior on Hyperliquid using statistical and machine learning methods, rather than relying on simple correlations.

## Approach

### Data Engineering
- Resolved timestamp inconsistencies (UTC epoch vs daily data)
- Created lag-based momentum features
- Identified sentiment regime transitions

### Statistical Analysis
- Applied Mann–Whitney U test to compare return distributions
- Evaluated evidence for a potential "Fear premium"

### Machine Learning
- Used K-Means clustering to identify trader archetypes
- Trained a Random Forest model to predict next-day profitability
- Used SHAP values for model interpretability

### Validation
- Performed Monte Carlo simulations (1,000 paths)
- Tested robustness of derived strategies under different scenarios

## **Repository Structure**
```text
PrimeTrade/
├── data/                       # Raw datasets (Sentiment.csv, Trader_Data.csv)
├── images/                     # Saved charts from the Jupyter Notebook
├── src/                        
│   └── data_preparation.py     # Clean, modular feature engineering script
├── output/                     # Generated intermediate files
├── notebooks/                  
│   └── Trail.ipynb             # The core analytical engine (Phases 1 through 3)
├── WRITEUP.md                  # 1-page business memo with insights & strategy rules
└── README.md                   # You are here
```

---

## **Setup & Execution**

### 1. Environment Setup
Create a virtual environment and install the required packages:
```bash
python3 -m venv venv
source venv/bin/activate
pip install pandas numpy scipy matplotlib seaborn scikit-learn shap jupyterlab
```

### 2. Running the Pipeline
Open the primary Jupyter Notebook to execute the entire pipeline step-by-step:
```bash
jupyter lab notebooks/Trail.ipynb
```
*Note: Ensure the `data/` directory contains both CSV files before running the notebook.*

---

## **Future Scopes**

1. Cox Survival Modeling:
   Model liquidation risk dynamically instead of using “Days Survived,” and test whether entering trades during Greed increases blow-up probability.
2. HMM for Regime Detection:
   Build a Hidden Markov Model on order flow to identify market regimes directly, avoiding reliance on external Fear/Greed indices.
3. Real-Time Trading Dashboard (Streamlit + API):
   Develop a live dashboard that flags when high-risk trader clusters take extreme long positions during Greed—serving as a contrarian short signal.
4. Interactive SHAP Dashboard:
   Create a UI where users can select any trader and instantly see a SHAP-based explanation of their risk profile.
