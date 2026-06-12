# Agentic AI Blood Donor Prediction and Recommendation System

**Author:** Vintth  
**Student ID:** A1931178  
**Institution:** Adelaide University  
**Program:** Master of Computer Science  


---

## Overview

A Blood Donor Prediction and Recommendation System built on the
**Self-Adaptive Agentic AI Framework**. The system predicts the
likelihood of a donor giving blood and recommends the most suitable
donors for outreach campaigns using a five-agent pipeline powered
by machine learning and large language models.

---

## Core Novelty

Cross-domain data fusion between the UCI Blood Transfusion dataset
and the MovieLens behavioural dataset. Human engagement behaviour
is transferable across domains — a person who consistently rates
movies exhibits the same habitual recurring engagement as a blood
donor. Both follow RFMT patterns — Recency, Frequency, Monetary,
and Time.

---

## System Architecture

<img width="1035" height="443" alt="Updated Architecture" src="https://github.com/user-attachments/assets/908b87b8-98c3-475c-a4f8-bf1828fd640e" />

---

## Results

| Metric | Value |
|---|---|
| Accuracy | 98.6% |
| F1 Score | 98.7% |
| AUC | 0.999 |
| Fairness Index | 0.900 |
| Task Completion Rate | 1.000 |
| Inter-Agent Agreement | 0.980 |
| Proactivity Score | 0.358 |
| Explanation Quality | 0.900 |
| Best Model | CatBoost |
| Active Agents | 5 |

---

## Datasets

All datasets are located in the `/datasets` folder.

| Dataset | File | Records | Source |
|---|---|---|---|
| UCI Blood Transfusion | transfusion.csv | 748 | UCI ML Repository |
| MovieLens Ratings | ratings.csv | 100,836 | GroupLens Research |
| MovieLens Movies | movies.csv | 9,742 | GroupLens Research |
| MovieLens Tags | tags.csv | 3,683 | GroupLens Research |
| Merged Dataset | merged_dataset.csv | 1,143 | Combined |

---

---

## Installation

```bash
pip install -r requirements.txt
```

---

## How to Run

1. Open `agentic_ai_research_project_a1931178.ipynb` in Google Colab
2. Upload the dataset files from the `/datasets` folder
3. Run all cells in order
4. The Gradio dashboard launches automatically at the end

---

## API Endpoints

| Endpoint | Method | Description |
|---|---|---|
| / | GET | Health check |
| /predict | POST | Predict donation probability |
| /recommend | POST | Get ranked recommendation |
| /metrics | GET | System performance metrics |
| /agents | GET | Agent descriptions |

### Sample API Request

```json
POST /predict
{
  "Recency": 2,
  "Frequency": 10,
  "Monetary": 2500,
  "Time": 35
}
```

### Sample API Response

```json
{
  "will_donate": true,
  "probability": 0.823,
  "recommendation": "High priority"
}
```

---

## Agent Pipeline

| Agent | Role |
|---|---|
| Communication Agent | Coordinates all models, computes softmax weights, selects best model dynamically |
| Retrieval Agent | Filters donors with Recency less than 12 months |
| Planner Agent | Ranks donors using weighted ML probability and final score formula |
| Fairness Agent | Balances frequent and infrequent donor representation |
| Explainer Agent | Generates plain English explanations for healthcare workers |

---

## Machine Learning Models

| Model | Accuracy | F1 Score | AUC |
|---|---|---|---|
| Logistic Regression | 0.944 | 0.947 | 0.957 |
| Random Forest | 0.986 | 0.986 | 0.998 |
| XGBoost | 0.986 | 0.986 | 0.998 |
| LightGBM | 0.986 | 0.986 | 0.998 |
| CatBoost | 0.986 | 0.987 | 0.999 |
| Extra Trees | 0.986 | 0.986 | 0.998 |
| Stacking Ensemble | 0.986 | 0.987 | 0.999 |

---

## Literature Comparison

| System | AUC | F1 | Fairness | Explainability | Proactivity |
|---|---|---|---|---|---|
| Classical ML | 0.75-0.81 | 0.55-0.65 | ≤0.90 | Minimal | Absent |
| Agentic Systems | 0.75-0.81 | 0.60-0.70 | ≤0.95 | Partial | Partial |
| This Work | 0.999 | 0.987 | 0.900 | Full | Full |

---

## Gradio Dashboard Tabs

| Tab | Description |
|---|---|
| Blood Request | Hospital inputs blood group and urgency to find matched donors |
| Agent Workflow | Runs the full five-agent pipeline for any selected donor |
| Communication Centre | Sends donation invitations and tracks the log |
| Donor Responses | Updates donor status as Accepted, Declined, or Pending |
| Activity Log | Live running log of all agent actions with timestamps |
| Research Analytics | Metric cards, radar chart, model comparison, ablation study |


