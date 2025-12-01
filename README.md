Fake job postings are increasingly common on online recruitment platforms and often lead to data theft or financial scams. This project builds a machine-learning system that automatically identifies fraudulent job advertisements using natural language processing (NLP) and classification algorithms. The full pipeline includes data preprocessing, TF-IDF feature extraction, metadata encoding, model training, evaluation, and saving the final optimized model.

📂 Dataset

Source: Kaggle

Name: Real or Fake? Fake Job Posting Prediction

Link: https://www.kaggle.com/datasets/shivamb/real-or-fake-fake-jobposting-prediction

The dataset contains 17,880 job postings, including text fields (title, description, requirements, company profile) and metadata such as employment type, experience, and industry.
Labels:

0 → Real job

1 → Fake job

⚙️ Methodology
1. Data Loading & EDA

Inspect dataset structure

Count real vs fake job posts

Analyze missing values

Preview sample job ads

2. Text Preprocessing

Lowercasing

Removing URLs, emails, symbols

Stopword removal

Lemmatization

Combining text features into one column

3. Feature Engineering

TF-IDF vectorization (20,000 features)

One-Hot Encoding of metadata

Dimensionality reduction (SVD for tree models)

4. Machine Learning Models

Trained and compared:

Logistic Regression

Linear SVM

Random Forest

XGBoost

Balanced models (class weights)

SMOTE oversampling

5. Evaluation Metrics

Accuracy

Precision, Recall, F1-score

Confusion Matrix

ROC-AUC

🧠 Best Model

The XGBoost model provided the best performance across all major metrics.

XGBoost Performance

Accuracy: 0.981

ROC-AUC: 0.968

Fake Job Recall: 0.62

Fake Job F1-score: 0.76

Final model saved as:

best_fake_job_model.pkl

📈 Discussion

Machine learning successfully distinguished real and fake job postings by leveraging both text and metadata. While Logistic Regression and SVM achieved strong baselines, ensemble models—especially XGBoost—captured deeper non-linear patterns common in fraudulent posts.

Handling class imbalance using class weights and SMOTE improved minority-class recall, showing that balancing strategies are essential in real-world imbalanced datasets.

XGBoost offered the best balance between detection power and low false positives, making it suitable for deployment.

🚀 Future Work

Use transformer-based models (BERT, RoBERTa) for improved semantic understanding

Apply advanced imbalance techniques (Adaptive Boosting, Focal Loss)

Deploy as an API or real-time dashboard to screen job posts automatically
