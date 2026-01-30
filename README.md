# Large-Scale User Behavior Modeling &amp; Causal Impact Analysis Platform

A production-style analytics and experimentation platform that simulates large-scale user behavior, builds SQL analaytics pipeline, and quantifies causal impact of product changes using modern statistical and ML methods.

## 📌 1. Project Overview
### Core Question:
👉 How do product changes affect user engagement, retention and monetization at scale?
This project simulates a Youtube/Airbnv/Spotify-like product, generates large-scale user event logs (10M+ rows), builds a data warehouse, transforms data using SQL/dbt, and applies statistical modeling and causal inference to quantify product impact.
The goal is to replicate the workflow of a **Product Data Scientist / Experimentation Scientist** at Google, Meta, or Airbnb.

## 🎯 2. What This Signals to Recruiters
This project demonstrates:
- End-to-end analytics system desin (ingestion -> warehouse -> modeling -> dashboard)
- SQL pipeline for cohorts, funnels, and retention
- Statistical modeling (linear, multivariate, stochastic)
- Machine Learning on large behavioral data
- Sampling, uncertainty estimation, and biad correction
- Causal inference and experimentation analysis
- Product decison-making via written memos

## 🏗️ 3. System Architecture
>> Synthetic Event Generator -> Postgres Warehouse -> dbt Transformations ->
>> Python Modeling & Causaul Analysis -> Streamlit Dashboard -> Decision Memo

Components
<img width="504" height="297" alt="image" src="https://github.com/user-attachments/assets/663b7925-8ced-430d-a5cb-9aecdb27374a" />

## 📊 4. Dataset Design
Synthetic Large-Scale User Events (10M+ rows)
**Users Table**
- user_id
- signup_time
- acquisition_channel
- country
- device_type

**Events Table**
- user_id
- event_time
- event_name (view, search, play, add_to_cart, purchase, like)
- session_id
- experiment_id
- variant (control / treatment)
- platform, geo, device

**Sessions Table (Derived)**
- session_start, session_end
- session_length
- primary_intent

## 🧮 5. Statistical & ML Modeling
### 5.1 Linear & Multivariate Models
- Linerar regression for engagement & revenue prediction
- Multivariate logistsic regression for churn prediction

### 5.2 Sampling & Uncertainty
- Stratified sampling for cohorts
- Boostrapping for confidence intervals
- Monet Carlo simulation for uncertianty modeling

### Stochastic Models
- Markov chains for session transitions
- Possion / Negative Binomial for event frequency modeling
- Coc Proportional Hazards model for churn survival analysis

### Machine Learning
- Gradient Boosting (LightGBM / XGBoost)
- Feature engineering pipelines
- Hyperparameter tuning
- Drift detection on behavior metrics

### 🗄️ 6. SQL & Data Engineering Layer
#### Core Analytics Table (dbt marts)
- daily_user_mertics
- retention_cohorts
- funnel_metrics
- experiment_daily_metrics

#### Example Metrics
- DAU / WAU / MAU
- D1 / D7 / D30 retention
- Funnel conversion rates
- Revenue per user
- Experiment lift and variance

### 🔬 7. Causal Impact & Experimentation
#### Experimental Setup
- User-level randomized A/B experiment
- Treatment effect injected in synthetic data

#### Causal Methods Implemented
- Naive difference in means
- Stratified lift estimation
- Boostrapped confidence intervals
- Cuped variance reduction
- Differnce-in-Differences (observational)
- Propensity Score Weighting (IPW)

### 📈 8. Dashboard (Streamlit)
#### Tabs
1. Overview - DAU, sessions, revenue trends
2. Retention - cohort retention heatmaps
3. Funnels - step conversion visualization
4. Experiment Impact - lift, CIs, CUPED-adjusted metrics
5. Behavior Drift - distribution AND PSI drift monitoring

#### 📑 9. Deliverables
- ✅ Production-style Github repo with data pipelines
- ✅ SQL warehouse schema and dbt DAG
- ✅ Python modeling modules
- ✅ Interactive Streamlit dashboard
- ✅ Technical report with statistical validation
- ✅ Product decision memo (ship / no-ship recommendation)

#### ⚙️ 10. How to Run the Project
##### 1. Start Postgres
docker compose up -d

##### 2. Generate synthetic events
python pipelines/generate_synthetic_events.py

##### 3. Load into Postgres
python pipelines/load_to_postgres.py

##### 4. Run dbt transformations
dbt run

##### 5. Launch dashboard
streamlit run app/streamlit_app.py

### 📁 11. Repository Structure
behavior-causal-platform/
  pipelines/
  dbt/
  analytics/
  app/
  reports/
  infra/
  README.md

### 🧠 12. Key Product Questions Answered
- Did the new feature increase engagement?
- What is the causal impact on retention and revenue?
- Which cohorts benefited the most?
- Are results statistically significant and robust?
- Should the feature be launched globally?

### 🧑‍💻 13. Future Extensions
- Real GA4 / BigQuery ingestion
- Real-time Kafka streaming pipleline
- Online experimentation monitoring
- Bayesion A/B testing
- Reinforcement learning for future optimization

### ✍️ 14. Author
Sajan Singh Shergill
MS Data Science, Pace University 
Product Data Scientist & AI Engineer Aspirant

This project replicates the real workflow of experimentation teams at large-scale tech companies and demonstrates production-level analytics, modeling and causal inference skills.
