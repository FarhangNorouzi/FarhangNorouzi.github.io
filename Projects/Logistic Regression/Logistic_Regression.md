## Credit Card Fraud Detection Using Logistic Regression

**Project Description:** The goal of this project is to create a Classification Model which predicts whether or not a person has presence of heart disease based on physical features of that person such as age,sex, cholesterol, etc...\
This project has been done as part of the *2021 Python for Machine Learning & Data Science Masterclass* online certificate on udemy.com


**DATA:** This database contains 14 physical attributes based on physical testing of a patient. Blood samples are taken and the patient also conducts a brief exercise test. The "goal" field refers to the presence of heart disease in the patient. It is integer (0 for no presence, 1 for presence). In general, to confirm 100% if a patient has heart disease can be quite an invasive process, so if we can create a model that accurately predicts the likelihood of heart disease, we can help avoid expensive and invasive procedures.

**Attribute Information:**
- age
- sex
- chest pain type (4 values)
- resting blood pressure
- serum cholestoral in mg/dl
- fasting blood sugar > 120 mg/dl
- resting electrocardiographic results (values 0,1,2)
- maximum heart rate achieved
- exercise induced angina
- oldpeak = ST depression induced by exercise relative to rest
- the slope of the peak exercise ST segment
- number of major vessels (0-3) colored by flourosopy
- thal: 3 = normal; 6 = fixed defect; 7 = reversable defect
- target:0 for no presence of heart disease, 1 for presence of heart disease
- Original Source: https://archive.ics.uci.edu/ml/datasets/Heart+Disease

**Creators:**
Hungarian Institute of Cardiology. Budapest: Andras Janosi, M.D. University Hospital, Zurich, Switzerland: William Steinbrunn, M.D. University Hospital, Basel, Switzerland: Matthias Pfisterer, M.D. V.A. Medical Center, Long Beach and Cleveland Clinic Foundation: Robert Detrano, M.D., Ph.D.

### Results

#### Confusion Matrix:

<img src="../../images/Logistic%20Regression/confusion_matrix.png?raw=true"/>

#### Precision Recall Curve:

<!--img src="images/Logistic%20Regression/precision_recall_curve.png?raw=true"/-->
<img src="../../images/Logistic%20Regression/precision_recall_curve.png?raw=true"/>

#### ROC Curve:

<img src="../../images/Logistic%20Regression/roc_curve.png?raw=true"/>

### Learning Outcomes:

