# **Integrated Banking Insights: Risk Assessment & Customer Behavior Optimization**

End-to-end Data Analytics & Machine Learning Project for Banking Institutions
**Tools:** Excel · Python · Scikit-Learn · Tableau · Docker · FastAPI

---

## 📌 **Overview**

This project delivers a comprehensive, production-ready analytics pipeline for a banking institution.
It integrates **machine learning**, **customer analytics**, **fraud detection**, and **interactive dashboards** to generate actionable business insights from **realistic banking transaction data (USA, 2023–2024)**.

The system includes:

- Fraud detection using ML (Random Forest / XGBoost)
- Customer segmentation using clustering (K-Means)
- Churn prediction & retention strategy modeling
- Loan eligibility & default risk analysis (secondary dataset)
- Tableau dashboards for CLV, profitability, and loan performance
- Dockerized ML prediction API ready for deployment

This project is designed to showcase advanced analytical, machine learning, and visualization skills for roles in **Data Science**, **Business Analytics**, **Risk Analytics**, and **ML Engineering**.

---

## 🚀 **Project Architecture**

```
banking-insights-project/
│
├── data/
│   ├── raw/
│   └── processed/
│
├── notebooks/
│   ├── 01_eda.ipynb
│   ├── 02_fraud_model.ipynb
│   ├── 03_segmentation_churn.ipynb
│
├── src/
│   ├── data_prep.py
│   ├── train_fraud_model.py
│   ├── train_churn_model.py
│   ├── train_segmentation.py
│   └── api.py
│
├── dashboards/
│   └── tableau_workbooks.twbx
│
├── Dockerfile
├── requirements.txt
└── README.md
```

---

## 🧹 **1. Data Preparation (Excel + Python)**

### ✔ Excel Steps:

- Clean and validate raw transaction data
- Identify missing values, outliers, and invalid entries
- Create pivot tables for:

  - Spend by category
  - Fraud rate by payment method
  - Monthly transaction trends

### ✔ Python Processing:

- Parsing dates & deriving time-based features
- Encoding categorical variables
- Outlier handling (99th percentile clipping)
- Creating customer-level aggregates (RFM metrics)

---

## 🔒 **2. Fraud Detection Module**

Built an ML pipeline to predict fraudulent transactions using:

- **Random Forest**
- **XGBoost**
- **Logistic Regression** (baseline)

### **Key Features Used:**

- Transaction amount, type, category
- Time features (hour, weekday, weekend)
- Customer demographics
- Behavioral features:

  - Avg spend (30 days)
  - Transaction frequency (24 hours)
  - Failed transaction count

### **Evaluation Metrics:**

- ROC-AUC
- Precision-Recall AUC
- Precision@Top-K high-risk transactions

### **Model Output:**

A probability score that indicates the likelihood of a transaction being fraudulent.

---

## 🏦 **3. Loan Eligibility & Risk Analysis**

A secondary loan dataset was used to model:

- Loan approval likelihood
- Probability of default
- Risk band segmentation (Low / Medium / High)

Models used:

- Logistic Regression
- Decision Tree / Random Forest

Dashboard includes default rate breakdown by income, loan amount, and tenure.

---

## 👥 **4. Customer & Marketing Analytics**

### **4.1 Customer Segmentation (K-Means)**

Created RFM + behavioral clusters:

- Recency: Days since last transaction
- Frequency: 90-day transaction count
- Monetary: Spend amount
- Category preferences (% spend)
- Demographics (age, income, occupation)

Typical segment outputs:

- **Young High-Spenders**
- **Mass Affluent Professionals**
- **Price-Sensitive Savers**

### **4.2 Customer Churn Prediction**

Defined churn as **no transactions in the last 90 days**.

Models used:

- Logistic Regression
- Random Forest
- Gradient Boosting / XGBoost

Metrics:

- ROC-AUC
- Recall for churned customers
- Churn probability distributions

---

## 📊 **5. Tableau Dashboards**

### ✔ **Loan Risk Dashboard**

- Filters: Loan type, region, tenure, income band
- Default heatmaps
- Portfolio risk KPIs

### ✔ **Customer Lifetime Value (CLV) Dashboard**

- CLV by customer segment
- Revenue distribution
- City-wise profitability

### ✔ **Fraud & Profitability Dashboard**

- Monthly fraud trend analysis
- Fraud rate by payment method
- Transaction amount vs fraud probability

---

## 🐳 **6. Dockerized Model Deployment**

ML models are served via a **FastAPI** backend.

### API Endpoints:

- `POST /predict_fraud`
- `POST /predict_churn`

### Example Dockerfile:

```dockerfile
FROM python:3.11-slim

WORKDIR /app
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

COPY src/ ./src
COPY models/ ./models

CMD ["uvicorn", "src.api:app", "--host", "0.0.0.0", "--port", "8000"]
```

Startup command:

```bash
docker build -t banking-insights .
docker run -p 8000:8000 banking-insights
```

---

## 📘 **7. Key Insights (Sample highlights)**

(_Replace with your actual results once you run the models_)

- Online transactions between **11 PM–4 AM** had a **2.7× higher fraud rate**
- Top **15% of customers generated 65%** of total revenue
- Churn model achieved **AUC ~0.82**, identifying 78% of at-risk high-value users
- Loan applicants with **unstable employment** showed **3.4× higher probability of default**

---

## 📝 **8. How to Run the Project**

### Install dependencies:

```bash
pip install -r requirements.txt
```

### Run notebooks for ML:

- `01_eda.ipynb`
- `02_fraud_model.ipynb`
- `03_segmentation_churn.ipynb`

### Start API:

```bash
uvicorn src.api:app --reload
```

### Launch Docker (optional):

```bash
docker build -t banking-insights .
docker run -p 8000:8000 banking-insights
```

---

## 🎯 **9. Skills Demonstrated**

- Data Cleaning (Excel, Pandas)
- Feature Engineering
- Machine Learning (Classification, Clustering)
- Fraud Detection & Risk Modeling
- Customer Segmentation & Churn Prediction
- Tableau Dashboard Development
- API Deployment (FastAPI)
- Docker Containerization
- Storytelling with Data

---

## 📄 **10. Ideal for Roles Like:**

- Data Analyst
- Business Analyst
- Risk Analyst
- ML Engineer
- Data Scientist
- Product Analytics

---

## ⭐ **11. Future Improvements**

- Add RNN/Temporal ML models for sequential fraud detection
- Build a real-time streaming pipeline using Kafka
- Integrate a SQL database for scalable storage
- Add uplift modeling for campaign optimization

---

## 📫 **Contact**

For queries, collaborations, or improvements, feel free to connect!
