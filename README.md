# Metabolic Syndrome Prediction Apply Machine Learning
---
- Quan Nguyen
- June 2023
---
![metabolic-syndrome-definition](https://github.com/J4sonN/MLprojects/assets/128573553/8e2093b2-16f6-4209-aac1-c15af4b98f50)
## Project Description

### Data Overview:

The dataset used for analysis was derived from the NHANES initiative, a renowned source of health data. Through careful data manipulation using SQL, we integrated several key variables from various tables. These variables encompassed factors such as abnormal waist circumference, triglyceride levels surpassing 150, HDL cholesterol below 50 in women or 40 in men, a history of hypertension, and mildly elevated fasting blood sugar falling between 100 and 125. To enhance the comprehensiveness of our model, we also incorporated numerous other variables, including uric acid, race, income, and more. While these additional factors hold the potential to contribute valuable insights, their precise impact remains uncertain until we rigorously test our model.

- Data source: [Metabolic Syndrome](https://data.world/informatics-edu/metabolic-syndrome-prediction) 

### Goal:
- The primary objective of this dataset is to predict the diagnosis of metabolic syndrome. Each row in the dataset represents the information of an individual patient. As a classification problem, the dataset lends itself to various analysis techniques.
- Apply clustering algorithms to facilitate optimal data discovery. By clustering the dataset, we can uncover inherent patterns and groupings that may provide valuable insights into the nature of metabolic syndrome.
- In addition to clustering, we will also utilize feature extraction techniques such as Principal Component Analysis (PCA). Feature extraction enables us to identify and prioritize the most influential variables within the dataset, thereby reducing dimensionality and enhancing model performance.
- Furthermore, feature engineering will be employed to engineer new features from the existing ones. This process involves deriving additional variables that may capture important relationships or interactions within the dataset. Through feature engineering, we can potentially uncover hidden patterns and create more informative representations of the data, ultimately aiding in the accurate prediction of metabolic syndrome.

### Dataset:

The dataset includes of 2401 rows, and 15 columns.The rows represent 2401 observations, and the columns represent 14 features and 1 target variable.

![Metabolic dictionaries](https://github.com/J4sonN/MLprojects/assets/128573553/11041fdf-6eff-4d5b-b737-39869c08565b)

### Explanatory Data Analysis
![scatter waistcir bmi](https://github.com/J4sonN/MLprojects/assets/128573553/bc423867-faa4-486b-b011-080707d4a647)
![scatter trigly bloodglucose](https://github.com/J4sonN/MLprojects/assets/128573553/a4dc4c8b-f27c-4051-b05d-18c87c7dabe5)

The correlation coefficient (r = 0.27) suggests a weak positive relationship between these two. Recognize that there might be other variables influencing the relationship between triglycerides and blood glucose. For example, factors like diet, physical activity, medication use, and underlying health conditions can affect both triglyceride and blood glucose levels. It's important to account for these variables and their potential impact on the relationship.

![scatter waistcir uricacid](https://github.com/J4sonN/MLprojects/assets/128573553/eebf95b7-d765-4491-a2dd-3fdaf7d81c32)

This strong correlation shows that the Waist circumference is correlated to the uric acid that found in our blood, so we can choose this correlation to recommend for stakeholders that patient can easily get hyperuricemia a.k.a gout when being overweight.

### Model Evaluation

#### Error Type:

For our Metabolic Syndrome dataset the positive class will be the presence of metabolic syndrome (MetSyn) and the negative (No MetSyn) class will be the absence of metabolic syndrome.

Type 1 error, also referred to as a false positive, occurs when our model incorrectly predicts the presence of metabolic syndrome despite its actual absence. Conversely, Type 2 error, also known as a false negative, happens when our model erroneously predicts the absence of metabolic syndrome despite its actual presence.

#### Score:

**Accuracy**

*accuracy is correct predictions our model made out of the total number of prediction*

![accuracy](https://github.com/J4sonN/MLprojects/assets/128573553/3ddee1f6-07ed-4367-acff-025e4c08c7f3)

**Recall**

*the score to reduce the number of false negatives*

![recall](https://github.com/J4sonN/MLprojects/assets/128573553/e51fc9c5-3b4b-49af-ad00-b4e3026adbd2)

**Precision**

*the score to reduce the number of false positives*
![precision](https://github.com/J4sonN/MLprojects/assets/128573553/b01718e8-fc20-41d5-9a52-2f7d0f51e023)

**F1-score**

*he performance of a classification model. It is the harmonic mean of precision and recall, providing a balanced measure of both metrics.*
![f1-score](https://github.com/J4sonN/MLprojects/assets/128573553/b8504253-b1c1-4430-b684-4590e4bca116)

#### Model comparision and recommendation:

![metrics](https://github.com/J4sonN/MLprojects/assets/128573553/3872ae14-440f-4d4d-8ad6-f2e25360f4b6)

- The Light GBM Classifier's best model with feature engineering is recommended due to its high evaluation metrics for both the testing and training datasets. Additionally, it has the lowest false negative rate compared to other models, which suggests that it is effective in reducing false predictions for metabolic syndrome.

- The Light GBM Classifier's best model with feature engineering exhibits strong overall performance and a good balance between accuracy and recall. It achieves high accuracy on both the training and testing datasets, indicating its ability to generalize well to unseen data. Moreover, its high recall indicates that it can successfully identify instances of metabolic syndrome, reducing the likelihood of false negatives.

- Considering these factors, this Light GBM Classifier's best model appears to be a promising choice for predicting metabolic syndrome based on the given evaluation metrics. However, it's essential to consider other factors such as model complexity, computational resources required, and specific requirements of your use case when making the final decision.

#### Clustering 
- Use Kmeans to establish a good number of cluster by age, bmi , bloodglucose columns.
- Explore each group for better understandings
- Combine all features

![newplot](https://github.com/J4sonN/MLprojects/assets/128573553/c5b9dae2-9c47-49ac-ace6-f68472cd1974)

The dataset has been clustered into four distinct groups:

- Cluster 0: Middle-aged patients with average income, highest waist circumference and BMI. They exhibit blood measurements indicating an average to high risk of health diseases and have a high likelihood of being detected with metabolic syndrome.

- Cluster 1: Young individuals with the highest income, lowest BMI, and waist circumference. Their blood measurements are the most favorable, resulting in the lowest likelihood of being detected with metabolic syndrome.

- Cluster 2: Middle-aged to older individuals with the lowest income. They have average BMI and waist circumference values, but their blood measurements indicate a relatively high risk. Consequently, they have the highest likelihood of being detected with metabolic syndrome.

- Cluster 3: Seniors with a high income, lower BMI and waist circumference compared to other clusters. However, their blood measurements are the worst among all clusters, leading to a high likelihood of being detected with metabolic syndrome.

## Personal Data Insight: 

Detecting metabolic syndrome early and providing prompt treatment can offer numerous benefits for individuals and public health. By identifying metabolic syndrome in its early stages, healthcare professionals can intervene with lifestyle modifications, medication, and targeted interventions to prevent or delay the progression of the condition. Early treatment can help individuals manage their blood pressure, blood sugar, cholesterol levels, and weight, reducing the risk of cardiovascular diseases, diabetes, and other related complications. Moreover, early detection and intervention can improve overall health outcomes, enhance quality of life, and potentially reduce healthcare costs by minimizing the need for intensive medical interventions and hospitalizations associated with advanced stages of metabolic syndrome. By focusing on early detection and timely treatment, we can make significant strides in preventing the detrimental consequences of metabolic syndrome and promoting better health for individuals and communities.
