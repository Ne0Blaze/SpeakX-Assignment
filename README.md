# SpeakX Assignment
Assignment for speakx. The deliverable include: a jupyter file containing the code and models, and a report containing findings, results and conclusions.

##Data
1. The data contains 7043 rows and 21 Columns, having no null values
2. Most of the data is Categorical in nature 

## EDA findings
1. The dataset is  highly imbalanced. There are 77% negative values and only 23% positive values. We need to us oversampling to balance the data for better model learning![image](https://github.com/Ne0Blaze/SpeakX-Assignment/assets/92355895/08320143-bd6d-4a9f-be56-991e2f5027de)

2. Numeric Colums show no significant correlation . There is a slight relationship between Monthly Charges and Total Charges but thats a given since MonthlyCharges influence Total Charges. There is a relationship between TotalCharges and Tenur ![image](https://github.com/Ne0Blaze/SpeakX-Assignment/assets/92355895/5e097c62-6930-4129-8127-129dbb27565f)

3. The data has even repesentation from both genders, married and batchlors. The data has a mejority of Young and Independent individuals![image](https://github.com/Ne0Blaze/SpeakX-Assignment/assets/92355895/215003a4-abaa-441d-8664-dca2dc979f01)

4. People with FiberOptic Internt Connection or Month-to-Month Contract are Churn more. People having Electronic check Churn more, and people having no Online Backup or Online security or Device protection tend to Churn more![image](https://github.com/Ne0Blaze/SpeakX-Assignment/assets/92355895/b80a9324-33e7-484a-9cd0-c6ec0e370c07)![image](https://github.com/Ne0Blaze/SpeakX-Assignment/assets/92355895/b8b7937b-be66-41a5-b55f-3ad095c79926)

5. There is a minor correlation between the variables and the target variable. To further check for independence between categorical columns we will have to use chi-square test. 


## Data cleaning and prep
- It is important to convert categorical values to numerical before moving on with models.Columns Having 2 classes can easily be converted into (0,1). ![image](https://github.com/Ne0Blaze/SpeakX-Assignment/assets/92355895/f96d266f-4962-4479-aaea-69ef62caaa82)
