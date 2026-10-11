# Social Media Use, Digital Addiction, and Sleep Analysis

This repository contains two related notebook analyses and Streamlit prediction dashboards:

1. A classification experiment for predicting the `addicted` label from digital-use and behavioral features.
2. A regression experiment for estimating sleep efficiency from social-media-use and sleep-related measurements.

These are separate datasets and modeling tasks; the classification and regression results should not be treated as one combined study.

## Project files

```text
.
├── Classification.ipynb
├── Classification dashboard.ipynb
├── Classification app.py
├── Classification_scaler.pkl
├── Regression.ipynb
├── Regression dashboard.ipynb
├── Regression app.py
├── mobile_addiction.csv
├── SocialMediaUsage_SleepLatencyAnalysis_Singapore.csv
├── stacked_model_with_scaler.pkl
├── linear_regression_model.pkl
├── regression_x_scaler.pkl
└── regression_y_scaler.pkl
```

The classification notebook compares Logistic Regression, K-Nearest Neighbors, and Random Forest; it also contains additional model experimentation. The regression notebook compares Linear Regression, Ridge, Random Forest, and polynomial regression for the selected sleep-efficiency target. The `Classification app.py` and `Regression app.py` files provide Streamlit interfaces that load the corresponding saved model artifacts.

## Run the dashboards

Use Python with pandas, NumPy, scikit-learn, joblib, and Streamlit installed. The notebook analyses also use Matplotlib, Seaborn, Plotly, and SciPy; dashboard notebooks additionally import Dash.

```bash
pip install streamlit pandas numpy scikit-learn joblib
streamlit run "Classification app.py"
```

For the sleep-efficiency interface:

```bash
streamlit run "Regression app.py"
```

To reproduce analysis, open the relevant `.ipynb` file in Jupyter and run it from the repository root so the relative CSV paths resolve. Saved `.pkl` files must remain alongside the apps as expected by their load calls.
Only load the checked-in pickle artifacts or files from sources you trust; Python pickle/joblib files can execute code during deserialization.

## Data and responsible use

The datasets include individual-level behavioral, demographic, and sleep-related fields (including participant IDs in the sleep dataset). Handle them according to their source license and privacy expectations; do not use model predictions as diagnoses or clinical advice.

Model quality, data provenance, and generalization need independent validation before any real-world use. The notebook-reported metrics are experimental results on the supplied data and are not guarantees for other populations.
