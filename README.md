# Aerogel-Bonding-296891
Assima Amangeldina, Ceyla Kaya, Lorenzo Cimmino


Our project focuses on the process of Aerogel Bonding with carbon fiber composites, which is the primary protection method in extreme temperatures in the development of lightweight, high-performance aerospace structures. This process ensures mechanical stability and thermal resistance. We will be evaluating the key parameters that affect the eligibility of Aerogel Bonding for commercial use. 


To begin our evaluation, we first implement Explanatory Data Analysis. (EDA)
We will be using a csv file which contains information like 'BondingSuccessful', 'BondingRiskRating', 'PercentageOfCompletedTasks', 'RequestedProcessAmount', 'TotalMaterialProcessed','working_skills', 'dependability', 'ProcessedKilograms', 'SkillRating', 'BondingPeriod'...etc. 
We load the data and inspect the data structures for each column. Then we check data integrity and begin cleaning the data. We look for missing values in each column and row while noting their data structure. We implement different heatmaps, graphs and pairplots to further analyze these values and their influence on the data. 

After analyzing this data, we assess that "BondingSuccessful" is the suitable target variable for our project because it focuses on the successful implementation of Aerogel Bonding, and this is the most important metric to consider compared to the others in the context of commercial use. Furthermore, we note that this is a classification problem. We gather the correlations of the columns with our target variable and select the ones we deem appropriate for our project. These columns are as follows:'ProcessedKilograms', # high positive correlation coefficient 0.53, 'BondingRiskRating', # high negative correlation coefficient -0.68, 'TotalChurnRisk', # moderate negative correlation coefficient -0.27, 'RequestedProcessAmount', # low negative correlation coefficient of -0.21, 'SkillRating', # low positive correlation coefficient 0.13 we keep this one for comparison purposes, 'BondingPeriod', # very low negative correlation of -0.097 We fill the categorical missing values with the modes of the column (most repeated values) and the numerical missing values with the means of the column. 

Then, we split the data into training and test sets using these features in our code. We chose a structure of 70-30 because of the large size of our dataset. We place the features into X and our target variable into y and filter the dataset. After filtering, we calculate the distributions of these sets in the dataset. Later we scale the data using MinMaxScaler and apply this scale on our training and testing sets. This completes our preprocessing. 

In our experimentation, we aimed at gathering the most well-rounded analysis of different models for classification problems. Therefore, we decided it would be in our best interest to implement the 3 following models in our project: Random Forests, Logistic Regression, and ANN. 

These 3 models all have different strengths and weaknesses, therefore providing the best analysis. Random Forests is not considered the best for simplicity, whereas Logistic Regression excels at simplicity. Meanwhile ANN can outperform RF and LR in complex tasks and non-linear relationships. Overall, the main reasons of choosing each is as follows:  We will be focusing on most these metrics in our analysis. 

Logistic Regression is one of the most straightforward classification algorithms. It provides a probability of the target variable (likelihood of Bonding being Successful). Random Forests are excellent at avoiding overfitting and perform well even with noisy or incomplete data. It also allows you to assess the importance of different features in making the classification decision, which is valuable for understanding data patterns and improving model interpretability. Alternatively, ANNs can handle various data types, including structured data (tables), sequential data (date), and unstructured data.

In our experiments, we tried to use the same metrics for each of the models to implement a fair comparison. 
In our findings, we discovered that the most accurate model for our classification problem was Random Forests with an accuracy of 0.9487. This outperforms LR (0.9227) and ANN (0.9455). 
Our result for Random Forest is as follows: 
Accuracy: 0.9487

      Classification Report:
                precision    recall  f1-score   support

           0.0       0.97      0.96      0.97      4681
           1.0       0.87      0.90      0.88      1319

        accuracy                           0.95      6000
         macro avg       0.92      0.93      0.93      6000
      weighted avg       0.95      0.95      0.95      6000


      Confusion Matrix:
      [[4511  170]
       [ 138 1181]]

However, LR was the fastest with a running time of 0.4 seconds. 

We conclude from our project and findings that Random Forests for classification problems may be the best option for accuracy while Logistic Regression might be the speedier alternative. 
