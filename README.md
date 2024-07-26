# Best Machine Learning Models to Predict Osteoporosis Risk
## Project Overview
Osteoporosis is a severe condition characterized by weakened bones, leading to an increased risk of fractures. Early prediction and diagnosis can help in managing and preventing the condition, thereby improving the quality of life for at-risk individuals, particularly older women. This study aims to identify the best machine learning models to predict osteoporosis risk using a balanced dataset.

## About the dataset
The dataset offers comprehensive information on health factors influencing osteoporosis development, including demographic details, lifestyle choices, medical history, and bone health indicators. It aims to facilitate research in osteoporosis prediction, enabling machine learning models to identify individuals at risk. Analyzing factors like age, gender, hormonal changes, and lifestyle habits can help improve osteoporosis management and prevention strategies.

### Dataset Description
| Column                           | Description                                                |
|----------------------------------|------------------------------------------------------------|
| `ID`                             | Unique identifier for each patient                         |
| `Age`                            | Age of the patient                                         |
| `Gender`                         | Gender of the patient                                      |
| `Hormonal Changes`               | Whether the patient has undergone hormonal changes         |
| `Family History with Osteoporosis` | Whether the patient has a family history of osteoporosis   |
| `Race/Ethnicity`                 | Race or ethnicity of the patient                           |
| `Body Weight`                    | Weight details of the patient                              |
| `Calcium`                        | Calcium levels in the patient's body                       |
| `Vitamin D`                      | Vitamin D levels in the patient's body                     |
| `Physical Activity`              | Physical activity details of the patient                   |
| `Smoking`                        | Whether the patient smokes                                 |
| `Alcohol Consumption`            | Whether the patient consumes alcohol                       |
| `Medical Conditions`             | Medical conditions of the patient                          |
| `Medication`                     | Medication details of the patient                          |
| `Prior Fracture`                 | Whether the patient has had a prior fracture               |
| `Osteoporosis`                   | Whether the patient has osteoporosis                       |

## Methods
### Data Preprocessing
The dataset was carefully prepared to make it suitable for machine learning analysis. Initially, we converted all categorical data into numerical data because machine learning algorithms require numerical input. This conversion was done using a technique called label encoding, which assigns a unique number to each category. After encoding, we checked to ensure the conversion was correct by reviewing the unique values for each column.

Next, we organized the dataset by separating the features (information used for prediction) from the target variable (the outcome we want to predict). We excluded the Id column, as it was just an identifier, and the Osteoporosis column, as it was our target variable. This left us with a set of features (X) and a target variable (y).

To ensure that all the features were on a similar scale, we standardized the data. Standardizing adjusts the values so that they have a mean of zero and a standard deviation of one, which can help improve the performance of many machine learning algorithms.

The prepared data was then split into two parts: one for training the models (80% of the data) and one for testing them (20% of the data). This split helps us evaluate how well our models might perform on new, unseen data. We used a random seed to ensure that the data split was reproducible.

### Model Selection and Evaluation
We evaluated a variety of machine learning models to find the best one for predicting the risk of osteoporosis. The models we tested included Logistic Regression, Random Forest, AdaBoost, Gradient Boosting, XGBoost, LightGBM, CatBoost, HistGradientBoosting, NGBoost, and Support Vector Classifier. Each model has different strengths and characteristics, so it was important to test multiple models.

To compare these models, we used several performance measures: accuracy (how often the model is correct), precision (how many of the positive predictions are actually correct), recall (how many actual positives the model correctly identifies), F1 score (a balance between precision and recall), and AUC-ROC (a measure of the model's ability to distinguish between classes). We also looked at confusion matrices, which show the number of correct and incorrect predictions for each class. We also generated ROC curves for each model to visually compare their performance. The results were compiled into a table to provide a clear comparison of each model's strengths and weaknesses.

## Results

The evaluation of multiple machine learning models for predicting osteoporosis risk yielded the following performance metrics:

| Model                       | Accuracy | Precision | Recall   | F1 Score | AUC      |
|-----------------------------|----------|-----------|----------|----------|----------|
| Logistic Regression         | 0.803571 | 0.824468  | 0.778894 | 0.801034 | 0.895175 |
| Random Forest               | 0.844388 | 0.942308  | 0.738693 | 0.828169 | 0.891830 |
| AdaBoost                    | 0.903061 | 1.000000  | 0.809045 | 0.894444 | 0.909378 |
| Gradient Boosting           | 0.908163 | 0.993939  | 0.824121 | 0.901099 | 0.899732 |
| XGBoost                     | 0.867347 | 0.901639  | 0.829146 | 0.863874 | 0.905330 |
| LightGBM                    | 0.885204 | 0.937500  | 0.829146 | 0.880000 | 0.906007 |
| CatBoost                    | 0.905612 | 0.982143  | 0.829146 | 0.899183 | 0.896061 |
| HistGradientBoosting        | 0.880102 | 0.941860  | 0.814070 | 0.873315 | 0.905564 |
| NGBoost                     | 0.910714 | 1.000000  | 0.824121 | 0.903581 | 0.906905 |
| Support Vector Classifier   | 0.821429 | 0.872832  | 0.758794 | 0.811828 | 0.894056 |

### Analysis

The results indicate that the NGBoost model achieved the highest accuracy (91.07%), precision (100%), and F1 score (90.36%), with an AUC of 0.9069, making it the most effective model for predicting osteoporosis risk in this study. Gradient Boosting and AdaBoost also performed very well, with high accuracy and F1 scores, indicating their suitability for this task.

While the Random Forest model demonstrated high precision (94.23%), its recall was lower compared to other models, suggesting it was better at predicting negative cases than positive cases. The Support Vector Classifier, while achieving respectable metrics, was outperformed by the other models in terms of accuracy, precision, and recall.

Overall, the ensemble methods, particularly NGBoost, Gradient Boosting, and AdaBoost, showed superior performance, highlighting their effectiveness in handling complex classification tasks such as osteoporosis risk prediction. The consistency across various performance metrics suggests these models are robust and reliable for clinical application.


## Conclusions
