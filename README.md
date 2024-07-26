# Best Machine Learning Models to Predict Osteoporosis Risk

## Project Overview
Osteoporosis is a severe condition characterized by weakened bones, leading to an increased risk of fractures. Early prediction and diagnosis can help in managing and preventing the condition, thereby improving the quality of life for at-risk individuals, particularly older women. This study aims to identify the best machine learning models to predict osteoporosis risk using a balanced dataset.

## About the Dataset
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

**Table 1: Description of the dataset columns**

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

### Performance Metrics

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

**Table 2: Performance metrics of various machine learning models for predicting osteoporosis risk**

### Confusion Matrices

The following confusion matrices provide a visual representation of the performance of each model in distinguishing between cases of osteoporosis and non-osteoporosis.

#### Logistic Regression
![download (5)](https://github.com/user-attachments/assets/b3da5bbf-88f0-441e-82f0-fd157e44e94f)
- **True Positives (TP):** 155
- **True Negatives (TN):** 160
- **False Positives (FP):** 33
- **False Negatives (FN):** 44

#### Random Forest
![download (6)](https://github.com/user-attachments/assets/d4663b64-8257-4c01-a977-670df8294d89)
- **True Positives (TP):** 147
- **True Negatives (TN):** 184
- **False Positives (FP):** 9
- **False Negatives (FN):** 52

#### AdaBoost
![download (7)](https://github.com/user-attachments/assets/732412ea-0951-4e35-8022-4002bd661218)
- **True Positives (TP):** 161
- **True Negatives (TN):** 193
- **False Positives (FP):** 0
- **False Negatives (FN):** 38

#### Gradient Boosting
![download (8)](https://github.com/user-attachments/assets/24a6d8e9-6005-45f5-ae6a-cd3478ae455e)
- **True Positives (TP):** 164
- **True Negatives (TN):** 192
- **False Positives (FP):** 1
- **False Negatives (FN):** 35

#### XGBoost
![download (9)](https://github.com/user-attachments/assets/ca1514da-9222-4fca-9ff4-c6ebd3a7fe85)
- **True Positives (TP):** 165
- **True Negatives (TN):** 175
- **False Positives (FP):** 18
- **False Negatives (FN):** 34

#### LightGBM
![download (10)](https://github.com/user-attachments/assets/1c220e6e-7873-41ff-9e3b-fac026ed7c6a)
- **True Positives (TP):** 165
- **True Negatives (TN):** 182
- **False Positives (FP):** 11
- **False Negatives (FN):** 34

#### CatBoost
![download (11)](https://github.com/user-attachments/assets/9c7bdef0-3b83-46cd-b89f-bf54f8aa6e47)
- **True Positives (TP):** 165
- **True Negatives (TN):** 190
- **False Positives (FP):** 3
- **False Negatives (FN):** 34

#### HistGradientBoosting
![download (12)](https://github.com/user-attachments/assets/90d54d1b-b48c-4422-a94a-fdaeb989023b)
- **True Positives (TP):** 162
- **True Negatives (TN):** 183
- **False Positives (FP):** 10
- **False Negatives (FN):** 37

#### NGBoost
![download (13)](https://github.com/user-attachments/assets/1768f0f2-b589-4431-87ce-af605d5ef77a)
- **True Positives (TP):** 164
- **True Negatives (TN):** 193
- **False Positives (FP):** 0
- **False Negatives (FN):** 35

#### Support Vector Classifier
![download (14)](https://github.com/user-attachments/assets/e47867b4-671f-44bc-9331-56f3678c1f63)
- **True Positives (TP):** 151
- **True Negatives (TN):** 171
- **False Positives (FP):** 22
- **False Negatives (FN):** 48

## Analysis

The confusion matrices and Table 2 illustrate the performance of each model in terms of true positives, true negatives, false positives, and false negatives. 

- **NGBoost**: This model achieved the highest accuracy (91.07%), precision (100%), and F1 score (90.36%), with an AUC of 0.9069. The confusion matrix for NGBoost shows that it correctly identified all 193 non-osteoporosis cases (true negatives) and 164 out of 199 osteoporosis cases (true positives), with no false positives and 35 false negatives.
  
- **Gradient Boosting and AdaBoost**: Both models also performed very well, with high accuracy, precision, and F1 scores. The confusion matrices for these models show minimal false positives and a high number of true positives and true negatives.

- **Random Forest**: This model demonstrated high precision (94.23%), indicating it was very effective at identifying non-osteoporosis cases. However, it had a lower recall compared to other models, meaning it missed a higher number of osteoporosis cases (false negatives).

- **Support Vector Classifier**: While achieving respectable metrics, this model was outperformed by the other models in terms of accuracy, precision, and recall. Its confusion matrix shows a relatively higher number of false positives and false negatives compared to the top-performing models.

- **Logistic Regression**: This model showed a balanced performance with decent accuracy, precision, recall, and F1 score, making it a reliable baseline model.

- **XGBoost and LightGBM**: These models also performed well, demonstrating high accuracy and balanced precision and recall, making them strong contenders for clinical application.

- **CatBoost and HistGradientBoosting**: Both models showed robust performance with high accuracy and F1 scores, indicating their reliability in predicting osteoporosis risk.

Overall, the ensemble methods, particularly NGBoost, Gradient Boosting, and AdaBoost, showed superior performance, highlighting their effectiveness in handling complex classification tasks such as osteoporosis risk prediction. The consistency across various performance metrics suggests these models are robust and reliable for clinical application.

## Discussion

The results from this study indicate that ensemble methods, particularly NGBoost, Gradient Boosting, and AdaBoost, are highly effective in predicting osteoporosis risk. These models consistently demonstrated high accuracy, precision, recall, and F1 scores, which are crucial metrics for evaluating model performance in binary classification tasks. The use of these models could potentially enhance early diagnosis and intervention strategies for osteoporosis, ultimately improving patient outcomes.

### Strengths of Ensemble Methods

Ensemble methods, such as NGBoost, Gradient Boosting, and AdaBoost, combine the predictions of multiple base learners to produce a single robust model. This approach tends to reduce variance and bias, leading to improved generalization on unseen data. The confusion matrices for these models show a minimal number of false positives and false negatives, highlighting their ability to accurately distinguish between osteoporosis and non-osteoporosis cases.

### Comparison with Other Models

While traditional models like Logistic Regression and Support Vector Classifier also performed reasonably well, they were outperformed by the ensemble methods in most metrics. The Random Forest model, although showing high precision, had a relatively lower recall, suggesting that it missed a significant number of positive osteoporosis cases. This highlights the importance of considering multiple performance metrics when evaluating model effectiveness, as high precision alone does not guarantee overall model reliability.

### Clinical Implications

The ability to accurately predict osteoporosis risk has significant clinical implications. Early identification of at-risk individuals allows for timely intervention, which can include lifestyle changes, medication, and other preventive measures to reduce the likelihood of fractures and other complications associated with osteoporosis. Implementing these machine learning models in clinical settings could provide healthcare professionals with a powerful tool for improving patient care and outcomes.

### Limitations and Future Work

Despite the promising results, this study has some limitations. The dataset, although balanced, may not capture all the nuances of the diverse patient population. Future research should consider using larger and more diverse datasets to validate the findings further. Additionally, integrating other predictive features, such as genetic markers or advanced imaging data, could potentially enhance the model's accuracy and reliability.

Future work could also explore the integration of these models into electronic health record systems to provide real-time risk assessments. Further studies should also investigate the long-term impact of using these predictive models on patient outcomes and healthcare costs.

## Conclusions

The findings of this study suggest that NGBoost, Gradient Boosting, and AdaBoost are the most effective machine learning models for predicting osteoporosis risk. These models demonstrated high accuracy, precision, recall, and F1 scores, making them suitable for clinical applications in osteoporosis risk prediction. The superior performance of these ensemble methods highlights their potential to be integrated into healthcare systems to aid in early diagnosis and intervention, ultimately improving patient outcomes.

The study underscores the importance of using a combination of performance metrics to evaluate model effectiveness and the need for further research to validate and enhance these models. By leveraging the strengths of machine learning, particularly ensemble methods, healthcare providers can significantly improve the management and prevention of osteoporosis, leading to better health outcomes for patients at risk of this debilitating condition.





