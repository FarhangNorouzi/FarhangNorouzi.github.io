## Credit Card Fraud Detection Using Logistic Regression

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
- Num of Samples: 284807 
- Num of Features: 31  

-Integer Variables:  
 variables: 1 --> ['Class']  

-Float Variables: 
 variables: 30 --> ['Time', 'V1', 'V2', 'V3', 'V4', 'V5', 'V6', 'V7', 'V8', 'V9', 'V10', 'V11', 'V12', 'V13', 'V14', 'V15', 'V16', 'V17', 'V18', 'V19', 'V20', 'V21', 'V22', 'V23', 'V24', 'V25', 'V26', 'V27', 'V28', 'Amount'] 

Is there any missing values? No missing value❌

**Data Imbalance:** The number of the Fraud transactions is ver small comparing to the total number of transactions (0.172%), which makes the data highly IMBALANCED toward one Class. Therefore, some pre-procesings need to be done before tarning the model, otherwise the predictive model will probably overfit toward the Non-Fraud class.

<img src="Distribution of Fraud vs Ligit Transactions.png?raw=true"/>
<img src="unblanced.png?raw=true"/>


### Results

#### Confusion Matrix:

<img src="CNF_matrix_RFC.png?raw=true"/>
<img src="CNF_matrix_XGB.png?raw=true"/>
<img src="CNF_matrix_SVC.png?raw=true"/>

#### Precision Recall Curve:

<!--img src="images/Logistic%20Regression/precision_recall_curve.png?raw=true"/-->
<img src="precision_recall_curve_RFC.png?raw=true"/>
<img src="precision_recall_curve_XGB.png?raw=true"/>
<img src="precision_recall_curve_SVC.png?raw=true"/>

#### ROC Curve:

<img src="ROC_curve_RFC.png?raw=true"/>
<img src="ROC_curve_XGB.png?raw=true"/>
<img src="ROC_curve_SVC.png?raw=true"/>

### Learning Outcomes:

**Acknowledgements:**
The dataset has been collected and analysed during a research collaboration of Worldline and the Machine Learning Group (http://mlg.ulb.ac.be) of ULB (Université Libre de Bruxelles) on big data mining and fraud detection.
More details on current and past projects on related topics are available on https://www.researchgate.net/project/Fraud-detection-5 and the page of the DefeatFraud project

Please cite the following works:

Andrea Dal Pozzolo, Olivier Caelen, Reid A. Johnson and Gianluca Bontempi. Calibrating Probability with Undersampling for Unbalanced Classification. In Symposium on Computational Intelligence and Data Mining (CIDM), IEEE, 2015

Dal Pozzolo, Andrea; Caelen, Olivier; Le Borgne, Yann-Ael; Waterschoot, Serge; Bontempi, Gianluca. Learned lessons in credit card fraud detection from a practitioner perspective, Expert systems with applications,41,10,4915-4928,2014, Pergamon

Dal Pozzolo, Andrea; Boracchi, Giacomo; Caelen, Olivier; Alippi, Cesare; Bontempi, Gianluca. Credit card fraud detection: a realistic modeling and a novel learning strategy, IEEE transactions on neural networks and learning systems,29,8,3784-3797,2018,IEEE

Dal Pozzolo, Andrea Adaptive Machine learning for credit card fraud detection ULB MLG PhD thesis (supervised by G. Bontempi)

Carcillo, Fabrizio; Dal Pozzolo, Andrea; Le Borgne, Yann-Aël; Caelen, Olivier; Mazzer, Yannis; Bontempi, Gianluca. Scarff: a scalable framework for streaming credit card fraud detection with Spark, Information fusion,41, 182-194,2018,Elsevier

Carcillo, Fabrizio; Le Borgne, Yann-Aël; Caelen, Olivier; Bontempi, Gianluca. Streaming active learning strategies for real-life credit card fraud detection: assessment and visualization, International Journal of Data Science and Analytics, 5,4,285-300,2018,Springer International Publishing

Bertrand Lebichot, Yann-Aël Le Borgne, Liyun He, Frederic Oblé, Gianluca Bontempi Deep-Learning Domain Adaptation Techniques for Credit Cards Fraud Detection, INNSBDDL 2019: Recent Advances in Big Data and Deep Learning, pp 78-88, 2019

Fabrizio Carcillo, Yann-Aël Le Borgne, Olivier Caelen, Frederic Oblé, Gianluca Bontempi Combining Unsupervised and Supervised Learning in Credit Card Fraud Detection Information Sciences, 2019

Yann-Aël Le Borgne, Gianluca Bontempi Machine Learning for Credit Card Fraud Detection - Practical Handbook
