<h1 align="center">AI & ML Project Portfolio</h1>
<p align="center">
  <em>6 end-to-end projects spanning Data Visualization · Clinical ML · Financial Forecasting · NLP · LLM Fine-tuning</em>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.10+-blue?style=for-the-badge&logo=python&logoColor=white"/>
  <img src="https://img.shields.io/badge/scikit--learn-ML-orange?style=for-the-badge&logo=scikit-learn&logoColor=white"/>
  <img src="https://img.shields.io/badge/HuggingFace-Transformers-yellow?style=for-the-badge&logo=huggingface&logoColor=black"/>
  <img src="https://img.shields.io/badge/Jupyter-Notebooks-F37626?style=for-the-badge&logo=jupyter&logoColor=white"/>
  <img src="https://img.shields.io/badge/Projects-6-brightgreen?style=for-the-badge"/>
</p>

---

## 📌 About This Repository

This repository contains 6 independently complete machine learning and AI projects built during my internship. The projects span the full ML spectrum — from classical supervised learning and ensemble methods, to LLM prompt engineering and transformer fine-tuning. Every notebook is self-contained with full EDA, model training, evaluation, and publication-quality visualizations.

---

## 🗂️ Project Index

| # | Project | Domain | Techniques | Dataset |
|---|---------|--------|------------|---------|
| 01 | [Iris Deep Visual Explorer](#-01--iris-deep-visual-explorer) | Data Visualization | PCA · LDA · Statistical EDA | Fisher's Iris (sklearn) |
| 02 | [Stock Price Prediction](#-02--stock-price-prediction) | Quantitative Finance | Stacked Ensemble · RSI · MACD · Bollinger Bands | AAPL via yfinance |
| 03 | [Heart Disease Classifier](#-03--heart-disease-classifier) | Clinical ML | 4-Model Benchmark · ROC-AUC · Feature Importance | UCI Cleveland |
| 04 | [Health Query Chatbot](#-04--general-health-query-chatbot) | NLP / LLM | Prompt Engineering · Two-Layer Safety Filter | Llama 3.1-8B (HuggingFace) |
| 05 | [Mental Health Chatbot](#-05--mental-health-support-chatbot) | NLP / Fine-Tuning | GPT-Neo Fine-tuning · Causal LM · EmpatheticDialogues | Facebook AI (25k convos) |
| 06 | [House Price Prediction](#-06--house-price-prediction) | Regression | Linear Regression · Gradient Boosting · 3-Method Importance | Kaggle Housing |

---

## 🛠️ Tech Stack

| Category | Tools |
|----------|-------|
| Languages | Python 3.10+ |
| ML / DL | scikit-learn, HuggingFace Transformers, PyTorch |
| Data | Pandas, NumPy, yfinance |
| Visualization | Matplotlib, Seaborn (custom dark theme) |
| NLP / LLM | Llama 3.1-8B (Inference API), GPT-Neo 125M (fine-tuned) |
| Environment | Jupyter Notebook |

---

## 📁 Repository Structure

```
AI-ML-Internship-DevelopersHub/
├── Task-1-Iris-Visualization/
│   ├── Iris-Analysis.ipynb
│   └── iris_dashboard.png
├── Task-2-Stock-Prediction/
│   ├── Stock-Prediction.ipynb
│   ├── fig1_eda_dashboard.png
│   ├── fig2_correlation.png
│   ├── fig3_feature_importance.png
│   ├── fig4_prediction_main.png
│   ├── fig5_scatter_error.png
│   ├── fig6_metrics_comparison.png
│   └── fig7_zoom_60day.png
├── Task-3-Heart-Disease/
│   ├── Heart-Disease-Prediction.ipynb
│   ├── heart.csv
│   └── heart_dashboard.png
├── Task-4-Health-Chatbot/
│   └── Health-Chatbot.ipynb
├── Task-5-Mental-Health-Chatbot/
│   └── Mental-Health-Chatbot.ipynb
├── Task-6-House-Price/
│   ├── House-Price.ipynb
│   ├── Housing.csv
│   └── house_price_dashboard.png
└── README.md
```



---

## 🔬 Projects In Detail

### 🌸 01 · Iris Deep Visual Explorer
📂 `Task-1-Iris-Visualization/`

A deep visual and statistical exploration of Fisher's Iris dataset, going far beyond basic plots. Ten-plus visualizations reveal the geometric separability of three flower species using scatter matrices, violin plots, correlation heatmaps, PCA, and LDA — all rendered in a custom dark theme.

**Highlights:**
- 10+ publication-quality visualizations with custom dark theme and species-distinct palette
- PCA and LDA applied for dimensionality reduction — shows *Iris setosa* is perfectly linearly separable in 1D
- No external dataset download — loads directly via `sklearn.datasets`

📦 **Libraries:** `numpy` `pandas` `matplotlib` `seaborn` `scikit-learn` `scipy`

---

### 🔮 02 · Stock Price Prediction
📂 `Task-2-Stock-Prediction/`

Predicts Apple Inc.'s (AAPL) next-day closing price using a stacked generalization ensemble — Random Forest + Gradient Boosting as base learners with Ridge Regression as a meta-learner. Data is pulled live from Yahoo Finance with no manual download required.

**Highlights:**
- Custom feature engineering: RSI, MACD, Bollinger Bands, 1–5 day lag features, log returns, rolling mean/std
- `TimeSeriesSplit` cross-validation (respects temporal ordering — no data leakage)
- Evaluated on MAE, RMSE, MAPE, and R²

> ⚠️ **Disclaimer:** Educational purposes only. Not financial advice.

📦 **Libraries:** `yfinance` `scikit-learn` `matplotlib` `seaborn` `pandas` `numpy`

---

### ❤️ 03 · Heart Disease Classifier
📂 `Task-3-Heart-Disease/`

A clinical binary classification study on the UCI Cleveland Heart Disease dataset (303 patients, 13 features). Four models are trained and benchmarked head-to-head, with evaluation including ROC curves, Precision-Recall curves, Confusion Matrices, and permutation-based feature importance.

**Highlights:**
- 4 models benchmarked: Logistic Regression, Decision Tree, Random Forest, Gradient Boosting
- Stratified K-Fold cross-validation for reliable estimates on a small clinical dataset
- Feature importance reveals `thal`, `ca`, and `oldpeak` as top predictors

> ⚠️ **Disclaimer:** Research only. Not a medical diagnostic tool.

📦 **Libraries:** `scikit-learn` `matplotlib` `seaborn` `pandas` `scipy`

---

### 🏥 04 · General Health Query Chatbot
📂 `Task-4-Health-Chatbot/`

An LLM-powered health information assistant built on Meta's Llama 3.1-8B-Instruct via the Hugging Face Inference API. The system is designed with a two-layer safety architecture that intercepts emergency and self-harm queries before they reach the model, then relies on a carefully engineered system prompt as a second guardrail layer. Maintains full multi-turn conversation history.

**Highlights:**
- Two-layer safety: rule-based keyword filter → LLM system prompt constraints
- Emergency responses include region-specific hotlines (Pakistan, UK, USA)
- System prompt enforces: no diagnoses, no prescription medications, always refer to a doctor
- Free to run — uses HuggingFace Inference API (no GPU required)

> ⚠️ **Disclaimer:** General information only. Not a substitute for professional medical advice.

📦 **Libraries:** `openai` (HuggingFace router)

---

### 🧠 05 · Mental Health Support Chatbot
📂 `Task-5-Mental-Health-Chatbot/`

Unlike prompt-engineered chatbot wrappers, this project fine-tunes a language model from scratch on real human empathetic conversations. GPT-Neo 125M is fine-tuned on Facebook AI's EmpatheticDialogues dataset (25,000 utterances across 32 emotions) using the HuggingFace Trainer API — teaching the model the emotional register and response style of supportive dialogue.

**Highlights:**
- Full fine-tuning pipeline: dataset loading → preprocessing → tokenization → Trainer API training
- Custom prompt format: `Emotion: {emotion}\nPerson: {prompt}\nSupportBot: {response}`
- Data visualization: emotion distribution across 32 categories, utterances-per-conversation histogram
- CPU/GPU compatible — auto-detects CUDA

> ⚠️ **Disclaimer:** Emotional support only. Not a substitute for professional mental health care.

📦 **Libraries:** `transformers` `datasets` `torch` `accelerate` `pandas` `matplotlib`

---

### 🏠 06 · House Price Prediction
📂 `Task-6-House-Price/`

Regression study on 545 property records predicting sale price from 13 structural and amenity features. Two models are benchmarked, and feature importance is analysed using three independent methods to determine which property attributes drive value most.

**Highlights:**
- Linear Regression vs Gradient Boosting head-to-head comparison
- Feature importance via 3 methods: model coefficients, permutation importance, and built-in tree importance
- Evaluated on MAE, RMSE, MAPE, and R²

📦 **Libraries:** `scikit-learn` `matplotlib` `seaborn` `pandas` `scipy` `numpy`

---

## 🚀 Getting Started

```bash
# Clone the repository
git clone https://github.com/RiyanKhan00/AI-ML-Internship-DevelopersHub.git
cd AI-ML-Internship-DevelopersHub

# Navigate to any project folder
cd Task-1-Iris-Visualization

# Install dependencies for that project (listed in each project's Libraries section above)
pip install numpy pandas matplotlib seaborn scikit-learn scipy

# Launch the notebook
jupyter notebook
```

---

## ⚙️ Requirements

- **Python 3.10+**
- **Jupyter Notebook** — install with `pip install notebook`
- **HuggingFace API Token** — required for Task 4 and Task 5
  - Create a free account at [huggingface.co](https://huggingface.co)
  - Go to **Settings → Access Tokens → New Token**
  - Paste it where prompted in the notebooks

---

## 👤 Author

**Riyan Khan**  
📧 riyankhan11101@gmail.com 
🔗 [LinkedIn](https://linkedin.com/in/riyan-khan-)
🐙 [GitHub](https://github.com/RiyanKhan00)

---

<p align="center">
  Found this useful? Give it a ⭐ — it helps others discover the repo.
</p>
