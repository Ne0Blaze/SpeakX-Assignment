# SpeakX Assignment
Assignment for speakx. The deliverable include: a jupyter file containing the code and models, and a report containing findings, results and conclusions.

## Data
1. The data contains 7043 rows and 21 Columns, having no null values
2. Most of the data is Categorical in nature 

## EDA findings
1. The dataset is  highly imbalanced. There are 77% negative values and only 23% positive values. We need to us oversampling to balance the data for better model learning  ![image](https://github.com/Ne0Blaze/SpeakX-Assignment/assets/92355895/08320143-bd6d-4a9f-be56-991e2f5027de)

2. Numeric Colums show no significant correlation . There is a slight relationship between Monthly Charges and Total Charges but thats a given since MonthlyCharges influence Total Charges. There is a relationship between TotalCharges and Tenur  ![image](https://github.com/Ne0Blaze/SpeakX-Assignment/assets/92355895/5e097c62-6930-4129-8127-129dbb27565f)

3. The data has even repesentation from both genders, married and batchlors. The data has a mejority of Young and Independent individuals  ![image](https://github.com/Ne0Blaze/SpeakX-Assignment/assets/92355895/215003a4-abaa-441d-8664-dca2dc979f01)

4. People with FiberOptic Internt Connection or Month-to-Month Contract are Churn more. People having Electronic check Churn more, and people having no Online Backup or Online security or Device protection tend to Churn more 
![image](https://github.com/Ne0Blaze/SpeakX-Assignment/assets/92355895/199bb265-df1f-425c-a2e7-7f6f5ece85a9)![image](https://github.com/Ne0Blaze/SpeakX-Assignment/assets/92355895/9b36b1d6-69d1-49b6-81e7-ea9aab414bb1)![image](https://github.com/Ne0Blaze/SpeakX-Assignment/assets/92355895/68f91f09-bc0d-4bec-b0a1-d5c3cfc0b068)

5. There is a minor correlation between the variables and the target variable. To further check for independence between categorical columns we will have to use chi-square test. 


## Data Preprocessing
- Data type of TotalCharges needs to be converted to numeric, which introduces null values that need to be dropped, and scalled for better performance  ![image](https://github.com/Ne0Blaze/SpeakX-Assignment/assets/92355895/154d81ae-aad1-40d6-91a9-e2dee06ebc7e) ![image](https://github.com/Ne0Blaze/SpeakX-Assignment/assets/92355895/e079b6f0-8a02-4127-96eb-90dc76522338)
- It is important to convert categorical values to numerical before moving on with models.Columns Having 2 classes can easily be converted into (0,1).  ![image](https://github.com/Ne0Blaze/SpeakX-Assignment/assets/92355895/f96d266f-4962-4479-aaea-69ef62caaa82)
- Other Non-Ordinal calsses are converted into numeric variable using one hot encoding  ![image](https://github.com/Ne0Blaze/SpeakX-Assignment/assets/92355895/ce6520e5-81f5-40d0-9949-27b66a803df8)
- Finally we perform a train test split on the data and use RandomOverSampler to oversample the train data to avoid bais in training.  ![image](https://github.com/Ne0Blaze/SpeakX-Assignment/assets/92355895/0c8e6c89-7eee-4de5-9edd-69a1ea61567b)


## Modeling 
- We will compare 5 models:
  1. KNN Classifier
  2. Logistic regression
  3. Random forests Classifier
  4. Support Vector Classifier
  5. Neural Network
 
- ### Knn Classifier
  K-Nearest Neighbors (KNN) algorithm used in machine learning for classification, works by storing a training dataset and classifying new data points based on their similarity to the data points in the training set.
  This algorithm gives us an accuracy of 70%.
   ![image](https://github.com/Ne0Blaze/SpeakX-Assignment/assets/92355895/7a0ff9fe-dc2b-40cb-a66a-a209429ede71)

- ### Logistic Regression Classifier
  Logistic regression models fits the data using a sigmoid function, and is often helpful in binary classification problems. They work by transforming a linear relationship between variables into a probability using a sigmoid function. This function outputs a value between 0 and 1, representing the likelihood of the positive outcome. This algorithm gives us an accuracy of 74% ![image](https://github.com/Ne0Blaze/SpeakX-Assignment/assets/92355895/f61f4481-2e16-4a46-9c3f-a3b9be4354ca)


- ### Random Forest Classifier
   RF classifier uses a group of decision trees to make the classification. Each tree analyzes a random subset of data and features. The final prediction is made by majority vote (classification) or averaging (regression) of the individual tree predictions. This algorithm gives us an accuracy of 78%.
   ![image](https://github.com/Ne0Blaze/SpeakX-Assignment/assets/92355895/b84f75d9-9e48-4583-ac6d-d9f5bb27eb05)

- ### Support Vector Classifier

  This algorythm finds a hyperplane that best separates different classes in high-dimensional space. This separation aims to maximize the margin between the data points and the hyperplane, leading to good generalization on unseen data. The algorithm is able to achive and accuracy of 74%.
  ![image](https://github.com/Ne0Blaze/SpeakX-Assignment/assets/92355895/792fdc50-fc90-4afa-8ce4-f72fc31b443b)

- ### Neural Network

  consist of interconnected nodes, like simplified neurons, that process information layer by layer. Neural networks learn by adjusting the weights between these connections. They are trained on data to recognize patterns and improve their accuracy over time. Using techniques like HyperParameter tuning we are able to achive an accuracy of 80%
![image](https://github.com/Ne0Blaze/SpeakX-Assignment/assets/92355895/bb53967d-fa7e-40fc-a012-b0d0c0e7c2ec)

### Model Report: 
All the models have almost same accuracy and metrics. We can achieve better accuracy by feature engineering techniques but its difficult to find correlation between categorical columns and their interactions can be ambiguous. 

| Models        | Accuracy |
----------------|-----------
| Knn Classifier |    78%   |
| Logistic Regresion | 77%  |
| Random Forest | 76% |
| SVC |  77%   |
| Neural Network | 80% |




## Challenges 
- The dataset is highly categorical which makes it difficult to find correlation between target and other columns
- Data is skewed towards the negative target class thus heavy oversampling is used.
- EDA proved to be challenging because there were many categorical values and finding a way to plot them meaningfully and extract insights from them is difficult.
   
## Conclusion
- In our case traditional ML algorithms like Logistic Regressiona(accuracy 77%) and Random forest(accuracy 76%) give a better precision and recall, compared to the marginal inprovement in accuracy given by Neural Network.
- There is not much data to work with if we want to create new features or even figure out how columns are correlated with each other.
- EDA and inital analysis lead to finding some interesting trends such as how different demogrpahics and services opted by people affect the churn prediction. 


