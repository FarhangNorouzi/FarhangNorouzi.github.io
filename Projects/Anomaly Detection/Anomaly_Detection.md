## Failure Prediction Using Anomaly Detection

**Project Description:** The goal of this project is to create an Anomaly Detection Model which can be used for Predictive Maintenance of machines and equipments by predicting the conditions causing Failure. Couple different anomaly detection methods have been used and a comparison among their performance is done.  
The dataset is chosen as one of the data science/machine learning competitions on kaggle.com.

**Introduction:** Modern world is full of numerous machines and equipment in various industries such as manufacturing, aviation, oil and gas among others. The lifecycle of all these equipment is limited, and they will run to failure at some point. An unexpected failure of a machine can cost millions of dollars in the big factory or plant. As a result, an efficient maintenance policy is needed to avoid the outages and breakdowns due to failure. The Preventive Maintenance, which is focused on replacing parts while they are still working, can reduce the total operational cost comparing to traditional Reactive Maintenance or replacing the parts after failure. The Predictive Maintenance became more and more feasible by the appearance of Machine Learning and AI techniques using the real-time data from IoT devices. These methods can constantly monitor the equipment’s health index and predict the point of failure in the future, based on the health of an equipment in the past. As a result, the replacement of parts can be scheduled just before the actual failure in order to reduce the downtime of the machines.


**DATA:** The dataset contains 3 different types of data:
- Timestamp data
- Telemetry Time Series Data including the 52 sensors of the water pump
- Machine status: The target label to be predicted when the failure will happen. The total dataset contains 220320 samples of the sensor data from April till September 2018 with the frequency of 1 minute. There are only 7 Failure (BROKEN status) points in the whole column of the 'machine_status' of the dataset.

**Attribute Information:**
- timestamp: Frequency equal to 1-minute 
- sensor_00 to sensor_51: IoT sensor data  
- machine_status: "NORMAL"+"RECOVERY"+"BROKEN"
- Original Source: https://www.kaggle.com/datasets/nphantawee/pump-sensor-data

**Dataset Summary:**
- Num of Samples: 220320 
- Num of Features: 53  

- Object Variables:  
 variables: 1 --> ['machine_status'] 

- Float Variables: 
 variables: 52 --> ['sensor_00', 'sensor_01', 'sensor_02', 'sensor_03', 'sensor_04', 'sensor_05', 'sensor_06', 'sensor_07', 'sensor_08', 'sensor_09', 'sensor_10', 'sensor_11', 'sensor_12', 'sensor_13', 'sensor_14', 'sensor_15', 'sensor_16', 'sensor_17', 'sensor_18', 'sensor_19', 'sensor_20', 'sensor_21', 'sensor_22', 'sensor_23', 'sensor_24', 'sensor_25', 'sensor_26', 'sensor_27', 'sensor_28', 'sensor_29', 'sensor_30', 'sensor_31', 'sensor_32', 'sensor_33', 'sensor_34', 'sensor_35', 'sensor_36', 'sensor_37', 'sensor_38', 'sensor_39', 'sensor_40', 'sensor_41', 'sensor_42', 'sensor_43', 'sensor_44', 'sensor_45', 'sensor_46', 'sensor_47', 'sensor_48', 'sensor_49', 'sensor_50', 'sensor_51'] 

- Is there any missing values? Data includes missing value✔️



**Dimensionality Reduction:** In order to reduce the dataset dimension which has too many features (sensors data features), a PCA method is applied to reduce the dimensionality. An Elbow method has been applied to find the best number of components and the eventually the 3 components (n_components=3) were chosen which explains almost 63% of the covariance of the original dataset. That much covariance would be sufficient for the sake of this project but one may go to higher dimensions if interested. After transforming the original data into the new orthogonal vectors PC1, PC2 and PC3, the dataframe looks like the following: 


<br> timestamp			  &nbsp; &nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp;     PC1  &nbsp;&nbsp;&nbsp;&nbsp;   PC2  &nbsp;&nbsp;&nbsp;&nbsp;    PC3
<br> 2018-04-01 00:00:00	-0.046056	0.490524	-0.470246
<br> 2018-04-01 00:01:00	-0.046056	0.490524	-0.470246
<br> 2018-04-01 00:02:00	-0.186309	0.500354	-0.441183
<br> 2018-04-01 00:03:00	-0.186651	0.538034	-0.489395
<br> 2018-04-01 00:04:00	-0.142655	0.645878	-0.355112


**Data Oversampling:** Oversampling is a technique to increases the number of minority class members in the training dataset. The main advantage of oversampling is that no information from the original training set is lost (in contrast with the undersampling method), so all observations from the minority and majority classes are kept. On the other hand, it is prone to overfitting. The so-called SMOTE (Synthetic Minority Oversampling Technique) method is implemented to make the dataset balanced. SMOTE creates synthetic points from the minority class (Fraud) to reach an equal balance between the minority and majority classes.

<img src="balanced.png?raw=true"/>

### Results

#### Isolation Forest:

<img src="Figures/PC1_plot_IF.png?raw=true"/>
<img src="Figures/PC2_plot_IF.png?raw=true"/>
<img src="Figures/PC3_plot_IF.png?raw=true"/>


#### One-Class SVM:

<img src="Figures/PC1_plot_OneSVM.png?raw=true"/>
<img src="Figures/PC2_plot_OneSVM.png?raw=true"/>
<img src="Figures/PC3_plot_OneSVM.png?raw=true"/>



### Learning Outcomes:
-	The best score belongs to Random Forest model (RFC) with the SMOTE oversampling data (0.89).
-	The other two models are slightly behind the RFC model.
-	SVC model has the potential to show a better performance if is trained on the full TRAIN set. In this example, the SVC classifier is trained on a smaller subset of training data to minimize the CPU runtime.

**Acknowledgements:**
The data is shared on kaggle.com as "pump_sensor_data".



