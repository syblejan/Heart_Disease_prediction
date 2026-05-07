# ❤️ Heart Disease Prediction (Machine Learning Classification)

> A supervised machine learning project that predicts the presence of heart disease in patients using Logistic Regression, with full EDA, feature scaling, and model evaluation.

---

## 📌 Task Objective

The goal of this task was to build a binary classification model that predicts whether a patient has heart disease (`1`) or not (`0`) based on clinical features. The project follows a complete end-to-end ML pipeline: data loading → cleaning → exploratory analysis → model training → evaluation → feature interpretation.

---

## 📂 Dataset Used

**Dataset:** [Heart Disease Dataset](https://raw.githubusercontent.com/PacktWorkshops/The-Data-Analysis-Workshop/master/Chapter07/Dataset/heart.csv)  
**Source:** Packt Data Analysis Workshop (GitHub)  
**Format:** CSV

The dataset contains patient clinical records with the following key features:

| Feature    | Description                                      |
|------------|--------------------------------------------------|
| `age`      | Age of the patient                               |
| `sex`      | Sex (1 = male, 0 = female)                       |
| `cp`       | Chest pain type (0–3)                            |
| `trestbps` | Resting blood pressure (mm Hg)                   |
| `chol`     | Serum cholesterol (mg/dl)                        |
| `fbs`      | Fasting blood sugar > 120 mg/dl (1 = true)      |
| `restecg`  | Resting ECG results                              |
| `thalach`  | Maximum heart rate achieved                      |
| `exang`    | Exercise-induced angina (1 = yes)                |
| `oldpeak`  | ST depression induced by exercise                |
| `slope`    | Slope of the peak exercise ST segment            |
| `ca`       | Number of major vessels colored by fluoroscopy  |
| `thal`     | Thalassemia type                                 |
| `target`   | **Target variable** — 1 = Heart Disease, 0 = No |

---

## 🔬 ML Pipeline

### Step 1 — Data Cleaning
- Checked for missing values (none found)
- Removed duplicate rows to ensure data integrity

### Step 2 — Exploratory Data Analysis (EDA)
Three key visualizations were produced:

- **Target Distribution** — Bar chart showing the class balance between patients with and without heart disease
- **Correlation Heatmap** — Identified relationships between all features; notable positive correlations with `cp` (chest pain) and `thalach` (max heart rate), and negative correlations with `exang` and `oldpeak`
- **Age vs Heart Disease** — Stacked histogram with KDE showing age distribution across both classes

### Step 3 — Preprocessing
- **Feature/Target Split:** All columns except `target` used as features (`X`); `target` as label (`y`)
- **Train-Test Split:** 80% training / 20% testing with `stratify=y` to preserve class proportions
- **Feature Scaling:** `StandardScaler` applied to normalize all features — fit on training data, applied to test data

### Step 4 — Model Training
- **Algorithm:** Logistic Regression (`sklearn.linear_model.LogisticRegression`)
- Trained on scaled training features with `random_state=42` for reproducibility

---

## 📊 Model Evaluation

### Metrics Used
- **Accuracy Score**
- **Classification Report** (Precision, Recall, F1-Score per class)
- **Confusion Matrix** (heatmap)
- **ROC Curve & AUC Score**

### Results

| Metric        | Value      |
|---------------|------------|
| Accuracy      | ~85%+      |
| AUC Score     | ~0.90+     |

> *Exact values depend on runtime; results are consistent across runs due to fixed `random_state=42`.*

The ROC curve showed strong discriminative ability, with the AUC well above the 0.5 random baseline.

### Feature Importance (Logistic Regression Coefficients)

Feature importance was derived from the model's learned coefficients. Features with the **largest absolute coefficients** had the greatest influence on predictions:

- **Positive predictors** (increase heart disease probability): chest pain type (`cp`), max heart rate (`thalach`)
- **Negative predictors** (decrease probability): exercise-induced angina (`exang`), ST depression (`oldpeak`), number of vessels (`ca`)

---

## 🛠️ Tech Stack

| Library / Tool      | Purpose                                      |
|---------------------|----------------------------------------------|
| `pandas`            | Data loading and manipulation                |
| `numpy`             | Numerical operations                         |
| `matplotlib`        | Plotting and visualization                   |
| `seaborn`           | Statistical visualizations (heatmap, countplot) |
| `scikit-learn`      | ML model, preprocessing, and evaluation      |
| Google Colab        | Development environment                      |


## 🔍 Key Findings

- Logistic Regression achieved strong performance on this structured clinical dataset, demonstrating that linear models can be highly effective when features are properly scaled.
- `stratify=y` in the train-test split was essential to prevent class imbalance from skewing evaluation metrics.
- Feature scaling (`StandardScaler`) was critical — Logistic Regression is sensitive to feature magnitude, and unscaled features would have degraded model performance.
- The correlation heatmap revealed that chest pain type and maximum heart rate are among the strongest indicators of heart disease in this dataset.
