# 🌊 Water Quality Prediction Pipeline Using Machine Learning

## 📌 Project Overview

This project develops a machine learning pipeline to predict **dissolved oxygen levels** in water using environmental sensor data collected from IoT devices.

Dissolved oxygen is one of the most important indicators of water quality. Low oxygen concentrations can harm aquatic ecosystems, affect biodiversity, and signal contamination.

Using Python and several regression algorithms, this project compares model performance and builds a reusable pipeline for predicting normalized dissolved oxygen values (`oxygen_scaled`).

This project demonstrates:

* Data cleaning and preprocessing
* Exploratory Data Analysis (EDA)
* Feature selection
* Model training and evaluation
* Pipeline creation for reproducibility

---

## 🎯 Project Objectives

The primary objectives of this project are to:

1. Analyze water quality sensor data.
2. Identify relationships among environmental variables.
3. Address multicollinearity among features.
4. Train and compare multiple regression models.
5. Select the best-performing model using RMSE.
6. Build a machine learning pipeline for repeatable predictions.

---

## 🗂️ Dataset Information

The notebook uses an Excel dataset named:

```text
Data IoTMLCQ.xlsx
```

### Key Variables

| Variable             | Description                    |
| -------------------- | ------------------------------ |
| `temperature`        | Water temperature              |
| `oxygen`             | Dissolved oxygen concentration |
| `turbid`             | Water turbidity                |
| `temperature_scaled` | Scaled temperature values      |
| `oxygen_scaled`      | Scaled target variable         |

### Target Variable

* `oxygen_scaled`

### Data Source

The dataset appears to be generated from **IoT-based water quality sensors**.

### Assumptions

* The data is clean enough for model development.
* Scaled variables were precomputed before loading.
* `oxygen_scaled` is used as the prediction target.

---

## 🛠️ Tools and Libraries Used

### Programming Language

* Python 3

### Libraries

* `pandas`
* `numpy`
* `matplotlib`
* `seaborn`
* `scikit-learn`
* `xgboost`
* `openpyxl`

### Machine Learning Models

* Linear Regression
* Random Forest Regressor
* Gradient Boosting Regressor
* XGBoost Regressor

---

## 🧹 Data Cleaning and Preparation

### Column Renaming

Some column names were translated from Spanish to English:

| Original Name | New Name      |
| ------------- | ------------- |
| `temperatura` | `temperature` |
| `oxigeno`     | `oxygen`      |
| `turbidez`    | `turbid`      |

### Handling Multicollinearity

A correlation heatmap was used to identify highly correlated features.

To reduce multicollinearity:

```python
df.drop(['temperature', 'oxygen'], axis=1, inplace=True)
```

This retained scaled versions while removing redundant variables.

---

## 📊 Exploratory Data Analysis (EDA)

The project includes:

* `df.head()` to inspect sample records.
* `df.info()` to review data types and missing values.
* `df.describe()` to summarize numerical distributions.
* Correlation heatmap using Seaborn.

### Key Analytical Question

> Which environmental variables best predict dissolved oxygen in water?

---

## 🤖 Machine Learning Workflow

### 1. Train-Test Split

* 80% training data
* 20% testing data

```python
train_test_split(X, Y, test_size=0.20)
```

### 2. Model Training

The following models were trained and evaluated:

* Linear Regression
* Random Forest Regressor
* Gradient Boosting Regressor
* XGBoost Regressor

### 3. Evaluation Metric

Model performance was measured using:

* Mean Squared Error (MSE)
* Root Mean Squared Error (RMSE)

RMSE was chosen because it expresses prediction error in the same scale as the target variable.

---

## 🔁 Pipeline Construction

A Scikit-learn `Pipeline` was built to package the best-performing model for reproducible training and prediction.

```python
pipeline = Pipeline([
    ('model', model_2)
])
```

Benefits of using a pipeline:

* Reproducibility
* Cleaner code
* Easier deployment
* Reduced risk of preprocessing inconsistencies

---

## 📈 Model Comparison Summary

| Model             | Purpose                           |
| ----------------- | --------------------------------- |
| Linear Regression | Baseline model                    |
| Random Forest     | Captures non-linear relationships |
| Gradient Boosting | Sequential error correction       |
| XGBoost           | Optimized gradient boosting       |

The best model is the one with the **lowest RMSE** on the test set.

---

## 🔍 Key Insights

* Water temperature and oxygen measurements were highly correlated.
* Removing redundant variables reduced multicollinearity.
* Ensemble models were expected to outperform linear regression.
* Machine learning can effectively model water quality dynamics from sensor data.

---

## 💡 Recommendations

1. Deploy the pipeline for real-time monitoring of water quality.
2. Integrate additional features such as pH, conductivity, and salinity.
3. Tune hyperparameters using `GridSearchCV` or `RandomizedSearchCV`.
4. Use cross-validation for more robust model assessment.
5. Build a dashboard in Power BI or Streamlit for visualization.

---

## 📁 Project Structure

```text
Water-Quality-Prediction/
│
├── Pipeline Project.ipynb        # Main notebook
├── Data IoTMLCQ.xlsx             # Sensor dataset
├── README.md                     # Project documentation
└── requirements.txt              # Python dependencies (optional)
```

---

## ▶️ How to Run This Project

### 1. Clone the Repository

```bash
git clone https://github.com/yourusername/water-quality-prediction.git
cd water-quality-prediction
```

### 2. Install Dependencies

```bash
pip install pandas numpy matplotlib seaborn scikit-learn xgboost openpyxl
```

### 3. Launch Jupyter Notebook

```bash
jupyter notebook
```

### 4. Open and Run

```text
Pipeline Project.ipynb
```

---

## 🌍 Business and Environmental Impact

This project has practical applications in:

* Environmental monitoring agencies
* Water treatment facilities
* Aquaculture operations
* Research institutions
* Smart city initiatives

Potential benefits include:

* Early detection of water quality deterioration
* Improved decision-making
* Reduced monitoring costs
* Better protection of aquatic ecosystems

---

## 👩‍💻 Author

**Miracle Ufuoma Uthunu**
Data Analyst | Chemistry Graduate | Environmental Data Enthusiast

---

## 📜 License

This project is licensed under the MIT License.

---

## ⭐ About This Project

This project combines my background in chemistry and environmental science with machine learning and data analytics to solve real-world water quality challenges.

If you found this project useful, consider starring the repository.

