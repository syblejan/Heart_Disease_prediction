# Heart Disease Prediction 🫀📊

Welcome to my AI/ML internship repository! This project focuses on building a predictive Machine Learning model to classify the presence of heart disease in patients based on various medical attributes.

## Task Objective
The main objective of this task is to develop a reliable classification model that can predict whether a patient is likely to have heart disease. This involves data preprocessing, exploratory data analysis (EDA), and model evaluation using statistical metrics.

## Dataset Used
* The project utilizes a Heart Disease dataset containing various medical indicators (such as blood pressure, cholesterol levels, max heart rate, etc.).
* **Data Preprocessing:** The features were scaled and normalized using `StandardScaler` to ensure the model performs optimally without bias toward features with larger scales.

## Models Applied
* **Logistic Regression:** Chosen for its efficiency in binary classification problems and interpretability of feature importance.
* Data was split into training and testing sets using `train_test_split` to validate the model's performance on unseen data.

## Key Results and Findings
* The Logistic Regression model achieved an accuracy of **[Insert %]** on the testing data.
* **Evaluation Metrics:** * Analyzed the **Confusion Matrix** to understand the rate of True Positives and False Negatives.
  * Generated a **Classification Report** detailing Precision, Recall, and F1-Score.
  * Visualized the model's performance using an **ROC Curve** and calculated the **AUC (Area Under the Curve)** to confirm the model's robust capability in distinguishing between the two classes.
