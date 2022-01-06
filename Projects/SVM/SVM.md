## Wine Fraud Detection Using SVM Method

**Project Description:** The overall goal is to use the wine dataset shown below to develop a machine learning model that attempts to predict if a wine is "Legit" or "Fraud" based on various chemical features.

**DATA:** This dataset contains 12 different chemical attributes such as acidity, density, pH etc... for about 6500 entries. The target label (quality) is strongly imbalanced toward the "Legit" label which makes the prediction challenging.   

**Attribute Information:**
- fixed acidity
- volatile acidity
- citric acid
- residual sugar
- chlorides
- free sulfur dioxide
- total sulfur dioxide
- density
- pH
- sulphates
- alcohol
- type
- quality (Legit or Fraud)

**Data Source:**
Data Source: P. Cortez, A. Cerdeira, F. Almeida, T. Matos and J. Reis. Modeling wine preferences by data mining from physicochemical properties. In Decision Support Systems, Elsevier, 47(4):547-553, 2009.
### Results

#### Confusion Matrix:

<img src="../../images/SVM/confusion_matrix_SVM.png?raw=true"/>

#### Precision Recall Curve:

<!--img src="images/Logistic%20Regression/precision_recall_curve.png?raw=true"/-->
<img src="../../images/SVM/precision_recall_curve_SVM.png?raw=true"/>

#### ROC Curve:

<img src="../../images/SVM/roc_curve_SVM.png?raw=true"/>

### Learning Outcomes:

