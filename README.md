# 🫀 Heart Disease Prediction
### Machine Learning Project by Abdullah | AI Student

---

## 📌 Overview
A Machine Learning model to predict heart disease severity using **Logistic Regression with Softmax function** built on the Cleveland Heart Disease Dataset.

The model classifies patients into 5 categories:
- **Class 0** → No Disease
- **Class 1** → Mild Disease
- **Class 2** → Moderate Disease
- **Class 3** → Serious Disease
- **Class 4** → Severe Disease

---

## 📂 Project Structure
```
heart-disease-prediction/
│
├── heart.csv                  # Cleveland Heart Disease Dataset
├── heart_disease.ipynb        # Main Jupyter Notebook
├── requirements.txt           # Required libraries
└── README.md                  # Project documentation
```

---

## 📊 Dataset
- **Source**: Cleveland Heart Disease Dataset (UCI ML Repository)
- **Features**: 14 clinical features
- **Target**: `num` (0–4 severity levels)

### Key Features Used:
| Feature | Description |
|---------|-------------|
| `age` | Age of patient |
| `sex` | Gender |
| `cp` | Chest pain type |
| `trestbps` | Resting blood pressure |
| `chol` | Cholesterol level |
| `thalach` | Maximum heart rate |
| `exang` | Exercise induced angina |
| `oldpeak` | ST depression |
| `ca` | Number of major vessels |
| `thal` | Thalassemia type |

---

## 🔧 Steps Performed

### 1. Exploratory Data Analysis (EDA)
- Checked dataset shape, data types, and statistics
- Identified missing values and duplicates

### 2. Correlation Analysis
- Generated a heatmap to find most correlated features with target
- **Top correlated features**: `ca` (0.52), `thal` (0.51), `oldpeak` (0.50), `cp` (0.40), `thalach` (-0.42)
- Dropped weak features: `fbs`, `chol`

### 3. Data Preprocessing
- Handled missing values
- Removed duplicates and outliers
- Feature scaling using **StandardScaler**
- Train/Test split (80/20)

### 4. Model Building
- **Algorithm**: Logistic Regression with Softmax (multinomial)
- **Solver**: lbfgs
- **Max iterations**: 1000

### 5. Handling Class Imbalance
- Applied **SMOTE** (Synthetic Minority Oversampling Technique)
- Balanced training data across all 5 classes

### 6. Model Evaluation
- Confusion Matrix
- Classification Report (Precision, Recall, F1-Score)

---

## 📈 Results

| Class | Precision | Recall | F1-Score | Support |
|-------|-----------|--------|----------|---------|
| 0 (No Disease) | 0.91 | 0.86 | **0.89** ✅ | 36 |
| 1 (Mild) | 0.25 | 0.22 | 0.24 ⚠️ | 9 |
| 2 (Moderate) | 0.12 | 0.20 | 0.15 ❌ | 5 |
| 3 (Serious) | 0.00 | 0.00 | 0.00 ❌ | 7 |
| 4 (Severe) | 0.00 | 0.00 | 0.00 ❌ | 3 |
| **Overall Accuracy** | | | **57%** | 60 |

---

## ⚡ Challenges Faced

1. **scikit-learn Version Conflict** — `multi_class` parameter removed in newer versions; resolved by removing it as Softmax is now applied automatically.

2. **Class Imbalance** — Class 0 had 36 samples while Class 4 had only 3 samples, making it very hard for the model to learn minority classes.

3. **Accuracy Drop after SMOTE** — Accuracy dropped from 60% to 57% after applying SMOTE. Learned that this is expected and F1-Score is a better metric for imbalanced data.

4. **Model Failing on Classes 3 & 4** — F1-Score of 0.00 due to extremely few samples in these classes.

---

## 💡 Key Learnings

- ✅ **F1-Score > Accuracy** for imbalanced datasets
- ✅ **StandardScaler** is essential for distance/gradient-based models
- ✅ **SMOTE** helps with imbalance but cannot replace real data
- ✅ Sometimes **binary classification** gives better results than multi-class when data is limited
- ✅ A model with lower accuracy but better F1-Score is more useful in healthcare

---

## 🛠️ Libraries Used

```
pandas
numpy
matplotlib
seaborn
scikit-learn
imbalanced-learn
jupyter
```

---

## 🚀 How to Run

```bash
# 1. Clone the repository
git clone https://github.com/YOUR_USERNAME/heart-disease-prediction.git

# 2. Navigate to project folder
cd heart-disease-prediction

# 3. Install required libraries
pip install -r requirements.txt

# 4. Open Jupyter Notebook
jupyter notebook heart_disease.ipynb
```

---

## 🔮 Future Improvements

- [ ] Convert to Binary Classification for better accuracy
- [ ] Try Random Forest and XGBoost models
- [ ] Get larger dataset with more minority class samples
- [ ] Build a web app using Flask or Streamlit
- [ ] Deploy model to cloud

---

## 👨‍💻 About Me
**Abdullah** — AI Student passionate about Machine Learning and Healthcare AI.

📧 Connect with me on [LinkedIn](#)

---

⭐ If you found this project helpful, please give it a star!
