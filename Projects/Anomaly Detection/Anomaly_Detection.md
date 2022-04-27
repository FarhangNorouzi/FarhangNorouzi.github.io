## Failure Prediction Using Anomaly Detection

**Project Description:** The goal of this project is to create a Classification Model which can detect the Fraud credit card transactions. Different classification methods have been used and a comparison among their performance is done.  
The dataset is chosen as one of the data science/machine learning competitions on kaggle.com.

**Introduction:** For credit card companies, it is important to recognize the fraudulent transactions and block them among the all other legit transactions. On the other hand, they should be able to reduce the number of their False Positive predictions, so the legit transactions would not be detected as Fraud. Therefore, a classification method which is able to accurately detect whether a transaction is a normal payment or a fraud would be vital for the financial institutes. 
In this project, various ML models are implemented and the classification results are compared to find the best performance among the models.      


**DATA:** The dataset contains transactions made by credit cards in September 2013 by European cardholders.
The whole transactions in the dataset occurred in two days, with 492 fraud transactions out of 284,807. Therefore, the dataset is highly unbalanced, toward the negative class (legit) where the positive class (frauds) accounts for 0.172% of all transactions.

The dataset contains only numerical input variables which are the outcome of a PCA transformation. The original features were not provided due to confidentiality issues. Features V1, V2, … V28 are the principal components obtained with PCA, where 'Time' and 'Amount' are the only features which have not been transformed. Feature 'Time' contains the seconds elapsed between each transaction and the first transaction. The feature 'Amount' is the corresponding amount for each transaction, an it can be used for example-dependant cost-sensitive learning. Feature 'Class' is the target variable and it takes value 1 in case of fraud and 0 otherwise.

**Attribute Information:**
- Amount : Transaction amount
- Time: seconds elapsed between each transaction 
- V1 to v28 : PCA obtained features  
- Class: 1 in case of fraud and 0 otherwise
- Original Source: https://archive.ics.uci.edu/ml/datasets/Heart+Disease

**Dataset Summary:**
------------DIMENSIONS ----------
Num of Samples: 220320 Num of Features: 53 

--------------DTYPES------------- 
Object Variables: 
 variables: 1 
 ['machine_status'] 

Float Variables: 
 variables: 52 
 ['sensor_00', 'sensor_01', 'sensor_02', 'sensor_03', 'sensor_04', 'sensor_05', 'sensor_06', 'sensor_07', 'sensor_08', 'sensor_09', 'sensor_10', 'sensor_11', 'sensor_12', 'sensor_13', 'sensor_14', 'sensor_15', 'sensor_16', 'sensor_17', 'sensor_18', 'sensor_19', 'sensor_20', 'sensor_21', 'sensor_22', 'sensor_23', 'sensor_24', 'sensor_25', 'sensor_26', 'sensor_27', 'sensor_28', 'sensor_29', 'sensor_30', 'sensor_31', 'sensor_32', 'sensor_33', 'sensor_34', 'sensor_35', 'sensor_36', 'sensor_37', 'sensor_38', 'sensor_39', 'sensor_40', 'sensor_41', 'sensor_42', 'sensor_43', 'sensor_44', 'sensor_45', 'sensor_46', 'sensor_47', 'sensor_48', 'sensor_49', 'sensor_50', 'sensor_51'] 

--------------MISSING VALUE----------
Is there any missing values? 
  Data includes missing value✔️ 


**Correlation Among Explanatory Features:** There are 3 non-PCA features (Time, Amount and Class) in the dataset. It is always a good idea to investigate the correlation between the various features to remove the features with HIGH correlation. This can avoid overfitting of the predictive model.

<img src="correlation.png?raw=true"/>

**Data Oversampling:** Oversampling is a technique to increases the number of minority class members in the training dataset. The main advantage of oversampling is that no information from the original training set is lost (in contrast with the undersampling method), so all observations from the minority and majority classes are kept. On the other hand, it is prone to overfitting. The so-called SMOTE (Synthetic Minority Oversampling Technique) method is implemented to make the dataset balanced. SMOTE creates synthetic points from the minority class (Fraud) to reach an equal balance between the minority and majority classes.

<img src="balanced.png?raw=true"/>

### Results

#### Isolation Forest:

<img src="Figures/PC1_plot_IF.png?raw=true"/>
<img src="Figures/PC2_plot_IF.png.PNG?raw=true"/>
<img src="Figures/PC3_plot_IF.png.png?raw=true"/>


#### One-Class SVM:

<img src="Figures/PC1_plot_OneSVM.png?raw=true"/>
<img src="Figures/PC2_plot_OneSVM.png.PNG?raw=true"/>
<img src="Figures/PC3_plot_OneSVM.png.png?raw=true"/>



### Learning Outcomes:
-	The best score belongs to Random Forest model (RFC) with the SMOTE oversampling data (0.89).
-	The other two models are slightly behind the RFC model.
-	SVC model has the potential to show a better performance if is trained on the full TRAIN set. In this example, the SVC classifier is trained on a smaller subset of training data to minimize the CPU runtime.

**Acknowledgements:**
The data is shared on kaggle.com as "pump_sensor_data".



