<<<<<<< HEAD
# Fraud-Transaction-Detection-Using-Transactions-Dataset
This Project builds a system that can classify if a transaction is fraudulent or not.
=======

---

## 💳 Fraud Detection System

### Overview :
This project builds a machine learning model to detect fraudulent transactions based on behavioral and transactional features. It supports financial institutions in identifying suspicious activity and preventing fraud in real time.

---

### Dataset Description :
The dataset includes anonymized transaction records with engineered features for fraud detection.

```
Key columns:
```
- `Time`: Time elapsed since the first transaction  
- `Amount`: Transaction amount  
- `V1` to `V28`: PCA-transformed features capturing behavioral patterns  
- `Class`: Target label (1 = Fraud, 0 = Legitimate)

---

### Workflow Summary :

#### 1. **Data Loading**
```python
df = pd.read_csv('/kaggle/input/fraud-detection-dataset/fraud.csv')
```

#### 2. **Preprocessing**
```python
df = df.dropna()
X = df.drop('Class', axis=1)
y = df['Class']
```

#### 3. **Train-Test Split**
```python
X_train, X_test, y_train, y_test = train_test_split(X, y, stratify=y, test_size=0.2, random_state=42)
```

#### 4. **Model Training**
```python
model = RandomForestClassifier(n_estimators=100, random_state=42)
model.fit(X_train, y_train)
```

#### 5. **Evaluation**
```python
y_pred = model.predict(X_test)
print(accuracy_score(y_test, y_pred))
print(classification_report(y_test, y_pred))
print(confusion_matrix(y_test, y_pred))
```

#### 6. **Prediction on New Transaction**
```python
input_df = pd.DataFrame(np.zeros((1, len(X_train.columns))), columns=X_train.columns)
# Fill in values based on confirmed X_train.columns
model.predict(input_df)
```

---

### Performance Metrics :
- **Accuracy**: ~99% on test data  
- **Precision**: High precision for fraud class  
- **Top predictors**: PCA components V14, V17, V10, and transaction amount

---

### Dependencies :
```bash
numpy
pandas
scikit-learn
```

---

### Author: Sushree Bandita Das
<h3 align="left"></h3> 
<p align="left">
  <a href="https://twitter.com/S_Bandita_Das" target="blank">
    <img align="center" src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/twitter.svg" alt="S_Bandita_Das" height="30" width="40" />
  </a>
  <a href="http://www.linkedin.com/in/sushree-bandita-das-160651309" target="blank">
    <img align="center" src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/linked-in-alt.svg" alt="sushree-bandita-das-160651309" height="30" width="40" />
  </a>
  <a href="https://github.com/SBanditaDas" target="blank">
    <img align="center" src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/github.svg" alt="SBanditaDas" height="30" width="40" />
  </a>
  <a href="https://www.kaggle.com/dasbanditasushree" target="blank">
    <img align="center" src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/kaggle.svg" alt="dasbanditasushree" height="30" width="40" />
  </a>

</p>

---
>>>>>>> 7a22181 (files added)
