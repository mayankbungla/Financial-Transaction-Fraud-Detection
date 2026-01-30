<div align="center">

<h1>💳 Financial Transaction Fraud Detection using Machine Learning</h1>

<p>
End-to-End Data Science Project for detecting fraudulent financial transactions using classical ML and XGBoost.
</p>

<hr>

</div>

<h2>📌 Project Overview</h2>

<p>
This project builds a complete Machine Learning pipeline to detect fraudulent financial transactions.
</p>

<ul>
<li>Understand transaction behavior</li>
<li>Perform exploratory data analysis</li>
<li>Engineer domain-driven features</li>
<li>Handle severe class imbalance</li>
<li>Compare multiple ML models</li>
<li>Select best performing algorithm</li>
<li>Provide actionable business insights</li>
</ul>

<p>
Dataset contains more than <b>6.3 million transactions</b> simulating 30 days of activity.
</p>

<p>
Binary Classification:
</p>

<ul>
<li><b>0</b> → Legitimate Transaction</li>
<li><b>1</b> → Fraudulent Transaction</li>
</ul>

<hr>

<h2>🚀 Key Highlights</h2>

<ul>
<li>Large scale dataset (6.3M+ rows)</li>
<li>Automated + manual EDA</li>
<li>Feature engineering using domain logic</li>
<li>Multicollinearity handled using VIF</li>
<li>Class imbalance solved using SMOTE</li>
<li>Multiple ML models evaluated</li>
<li>XGBoost selected as final model</li>
<li>Strong ROC-AUC performance</li>
<li>Business interpretation included</li>
</ul>

<hr>

<h2>📂 Repository Structure</h2>

<pre>
├── 00.ipynb                      # Automated EDA
├── 01.ipynb                      # ML Pipeline
├── Fraud.csv                     # Dataset
├── Data Dictionary.txt           # Column Info
├── fraud_detection_data_report.html
└── README.md
</pre>

<hr>

<h2>📊 Dataset Description</h2>

<table border="1" cellpadding="8">
<tr><th>Column</th><th>Description</th></tr>
<tr><td>step</td><td>Hour of transaction (1 step = 1 hour)</td></tr>
<tr><td>type</td><td>CASH_IN, CASH_OUT, PAYMENT, TRANSFER, DEBIT</td></tr>
<tr><td>amount</td><td>Transaction amount</td></tr>
<tr><td>nameOrig</td><td>Sender ID</td></tr>
<tr><td>oldbalanceOrg</td><td>Sender balance before</td></tr>
<tr><td>newbalanceOrig</td><td>Sender balance after</td></tr>
<tr><td>nameDest</td><td>Receiver ID</td></tr>
<tr><td>oldbalanceDest</td><td>Receiver balance before</td></tr>
<tr><td>newbalanceDest</td><td>Receiver balance after</td></tr>
<tr><td>isFraud</td><td>Target variable</td></tr>
<tr><td>isFlaggedFraud</td><td>Rule based fraud flag</td></tr>
</table>

<hr>

<h2>🧪 Exploratory Data Analysis</h2>

<ul>
<li>Pandas Profiling report</li>
<li>Statistical summaries</li>
<li>Distribution plots</li>
<li>Fraud vs Non-fraud analysis</li>
</ul>

<h3>Key Findings</h3>

<ul>
<li>Extreme class imbalance</li>
<li>Fraud appears only in CASH_OUT and TRANSFER</li>
<li>Fraud shows abnormal balance movements</li>
</ul>

<hr>

<h2>🛠 Feature Engineering</h2>

<p><b>Receiver credited amount</b></p>

<pre>
newbalanceDest - oldbalanceDest
</pre>

<p><b>Sender debited amount</b></p>

<pre>
oldbalanceOrg - newbalanceOrig
</pre>

<p>
These features capture real money flow and became strong predictors.
</p>

<hr>

<h2>🔗 Multicollinearity Handling</h2>

<p>Used correlation heatmap + Variance Inflation Factor (VIF)</p>

Removed columns:

<ul>
<li>oldbalanceOrg</li>
<li>newbalanceOrig</li>
<li>oldbalanceDest</li>
<li>newbalanceDest</li>
<li>nameOrig</li>
<li>nameDest</li>
<li>isFlaggedFraud</li>
</ul>

<hr>

<h2>⚖️ Class Imbalance</h2>

<p>
Handled using <b>SMOTE</b> (Synthetic Minority Oversampling Technique).
</p>

<p>
This prevents the model from biasing toward majority class.
</p>

<hr>

<h2>🤖 Models Evaluated</h2>

<ul>
<li>Logistic Regression</li>
<li>Decision Tree</li>
<li>Random Forest</li>
<li>Gradient Boosting</li>
<li>SVM</li>
<li>XGBoost</li>
</ul>

Metrics:

<ul>
<li>Accuracy</li>
<li>Precision</li>
<li>Recall</li>
<li>F1 Score</li>
<li>ROC-AUC</li>
</ul>

<p><b>Winner: XGBoost</b></p>

<hr>

<h2>📈 Final Model Performance</h2>

<ul>
<li>Accuracy ≈ 97%</li>
<li>Precision ≈ 97%</li>
<li>Recall ≈ 97%</li>
<li>F1 ≈ 97%</li>
<li>Strong ROC-AUC</li>
</ul>

<hr>

<h2>🧠 Key Fraud Indicators</h2>

<ul>
<li>CASH_OUT & TRANSFER dominance</li>
<li>Sender / Receiver balance mismatch</li>
<li>Sudden fund depletion</li>
</ul>

<hr>

<h2>🛡 Business Recommendations</h2>

<ul>
<li>Real-time ML scoring</li>
<li>Balance consistency checks</li>
<li>Extra verification on large transfers</li>
<li>Continuous retraining</li>
</ul>

<hr>

<h2>📏 Measuring Success</h2>

<ul>
<li>Fraud rate reduction</li>
<li>Alert precision</li>
<li>ROC-AUC stability</li>
<li>Periodic evaluation</li>
</ul>

<hr>

<h2>🧰 Tech Stack</h2>

<ul>
<li>Python</li>
<li>Pandas / NumPy</li>
<li>Scikit-Learn</li>
<li>XGBoost</li>
<li>Imbalanced-Learn</li>
<li>Matplotlib / Seaborn</li>
<li>Statsmodels</li>
<li>Pandas Profiling</li>
</ul>

<hr>

<h2>▶️ How To Run</h2>

<pre>
pip install pandas numpy scikit-learn imbalanced-learn xgboost seaborn matplotlib pandas-profiling
</pre>

<p>
Run:
</p>

<ul>
<li>00.ipynb → EDA</li>
<li>01.ipynb → ML Pipeline</li>
</ul>

<hr>

<h2>✨ Author</h2>

<p>
<b>Mayank Bungla</b><br>
Data Science | Machine Learning | Analytics
</p>
