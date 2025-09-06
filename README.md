# Employee-turnover-analytics
Predict employee turnover to help HR department identify at-risk employees and take proactive retention measures. Using historical employee data, this project builds machine learning models to identify patterns in satisfaction, evaluation, workload, promotions, and salary levels, and predicts the probability of employees leaving the company.

Project Steps
1. Exploratory Data Analysis (EDA)

Checked for missing values and basic statistics.

Visualized relationships between features and turnover:

Bar plots for number_project and department-wise turnover.

Correlation heatmaps of numerical features.

Observed that low satisfaction, high workload, and certain departments had higher turnover.

2. Preprocessing

One-hot encoded categorical columns (Department, salary).

Separated numerical and categorical features.

Handled class imbalance using SMOTE.

Stratified train-test split (80:20, random_state=123).

3. Clustering

K-Means clustering on employees who left, using satisfaction_level and last_evaluation.

Evaluated clusters using inertia and silhouette score.

Found 3 meaningful clusters:

Low satisfaction, low evaluation → disengaged employees.

Low satisfaction, high evaluation → overworked high performers.

Moderate satisfaction and evaluation → neutral group.

4. Model Training

Models trained:

Logistic Regression (with standardization and pipeline)

Random Forest Classifier

Gradient Boosting Classifier

Used 5-fold cross-validation.

Evaluated using Precision, Recall, F1-score, and ROC-AUC.

5. Model Evaluation

Random Forest had slightly better Recall than Gradient Boosting.

Precision and Recall were close for all models, but Recall is prioritized for HR to catch as many at-risk employees as possible.

ROC-AUC and PR curves were plotted for comparison.

6. Turnover Risk Categorization

Using the Random Forest model, employees in the test set were assigned turnover probabilities.

Categorized into four zones based on risk.
