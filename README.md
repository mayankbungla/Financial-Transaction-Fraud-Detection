<div align="center">

<img src="https://capsule-render.vercel.app/render?type=waving&color=auto&height=220&section=header&text=Fraud%20Detection%20Architecture&fontSize=50&animation=fadeIn" width="100%" />

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.9+-3776AB?style=for-the-badge&logo=python&logoColor=white" />
  <img src="https://img.shields.io/badge/XGBoost-Selected-008000?style=for-the-badge&logo=xgboost" />
  <img src="https://img.shields.io/badge/Dataset-6.3M%20Rows-blueviolet?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Business-FinTech-FF6600?style=for-the-badge" />
</p>

<h3>🕵️‍♂️ End-to-End Financial Transaction Fraud Detection</h3>
<p>
    An enterprise-level Machine Learning pipeline designed to identify fraudulent activity within <b>6.3 Million</b> transactions with surgical precision.
</p>

<a href="#-final-model-performance">View Performance</a> •
<a href="#-technical-methodology">Methodology</a> •
<a href="#-business-impact">Business Impact</a> •
<a href="https://huggingface.co/datasets/RegularGuyOIO/financial-transaction-fraud-dataset/blob/main/Fraud.csv">Download Dataset</a>

<hr />
</div>

## 📌 The Problem Landscape
Financial fraud costs global institutions billions annually. The primary technical hurdle in this project was the **"Needle in a Haystack"** problem: fraudulent transactions accounted for only **0.13%** of the entire dataset. 



## 🏗 Technical Methodology

### 1. Data Forensics & Cleaning
* **Volume:** Processed 6,362,620 rows across 11 features.
* **Multicollinearity:** Utilized **Variance Inflation Factor (VIF)** to identify and prune highly correlated features (like old/new balances) that would otherwise lead to overfit models.

### 2. Feature Engineering (Domain Logic)
Instead of relying on raw data, I engineered features that simulate the **Internal Logic** of a transaction:
* **Error in Origin:** Checks if the requested amount matches the actual balance deduction.
* **Error in Destination:** Checks if the receiver's account actually grew by the sent amount.

### 3. Solving Class Imbalance
To ensure the model didn't simply ignore the rare fraud cases, I implemented **SMOTE (Synthetic Minority Over-sampling Technique)**, effectively balancing the training set without losing critical information.



---

## 📊 Final Model Performance
After a rigorous comparison of 6 algorithms (Logistic Regression, Random Forest, SVM, etc.), **XGBoost** emerged as the superior architect.

<table align="center" border="1">
  <tr>
    <th align="center">Metric</th>
    <th align="center">Score</th>
    <th align="center">Significance</th>
  </tr>
  <tr>
    <td><b>Accuracy</b></td>
    <td align="center">97%</td>
    <td>Overall system correctness</td>
  </tr>
  <tr>
    <td><b>Precision</b></td>
    <td align="center">97%</td>
    <td>Minimizing False Positives (customer annoyance)</td>
  </tr>
  <tr>
    <td><b>Recall</b></td>
    <td align="center">97%</td>
    <td>Maximizing Detection (preventing financial loss)</td>
  </tr>
  <tr>
    <td><b>F1-Score</b></td>
    <td align="center">97%</td>
    <td>Balance between Precision and Recall</td>
  </tr>
</table>

---

## 🧠 Key Insights
* **The "Transfer-CashOut" Loop:** Fraudulent behavior is strictly limited to `TRANSFER` followed by an immediate `CASH_OUT`.
* **The Emptying Pattern:** Fraudsters almost always attempt to drain the account to exactly **0.00**.
* **Flag Efficiency:** The existing rule-based `isFlaggedFraud` caught almost nothing; the ML model is necessary for modern security.

<hr />

## 🛡 Business Impact & Recommendations
> **"Data is the fuel, but insights are the engine."**

1. **Real-time API Scoring:** Deploy the XGBoost model as a REST API for millisecond-latency scoring during the transaction "handshake."
2. **Behavioral Throttling:** Automatically flag transactions where the `newbalanceOrig` hits zero from a high starting balance.
3. **Adaptive Thresholds:** Dynamically adjust the model's sensitivity based on the `step` (hour of the day), as fraud patterns shift during night hours.

<hr />

## 🧰 Tech Stack
* **Language:** Python 3.9+
* **Frameworks:** Scikit-Learn, XGBoost, Statsmodels
* **Data Handling:** Pandas, NumPy
* **Visualization:** Matplotlib, Seaborn
* **Tools:** Pandas Profiling, Jupyter Notebooks

---

## ✨ Author
**Mayank Bungla**
*Data Scientist | Machine Learning Engineer*

<p align="left">
<a href="https://www.linkedin.com/in/mayankbungla/"><img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" /></a>
<a href="mailto:your-email@example.com"><img src="https://img.shields.io/badge/Gmail-D14836?style=for-the-badge&logo=gmail&logoColor=white" /></a>
</p>

<p align="center">
  <i>"I build systems that see patterns humans miss."</i>
</p>
