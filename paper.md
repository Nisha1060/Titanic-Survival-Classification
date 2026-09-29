# Titanic Survival Classification
## Abstract
This study investigates whether passenger characteristics and engineered family-related features can be used to predict Titanic survival. The experiment uses 891 passenger records and treats `Survived` as a binary target. After data cleaning, missing-value handling, categorical encoding, and feature engineering, two classification models—Logistic Regression and Random Forest—were trained and evaluated on the same held-out test set. Accuracy, Precision, Recall, and F1-score were used to compare model performance. The results provide a comparison between a linear classification approach and a tree-based ensemble approach for Titanic survival prediction.
## 1. Introduction
The Titanic dataset is a commonly used machine learning classification dataset containing information about passengers who travelled on the Titanic. Passenger characteristics such as class, sex, age, family information, fare, and port of embarkation can be used to investigate patterns associated with survival.
The research question of this study is:
> Can passenger characteristics and engineered family-related features be used to predict Titanic survival, and how do Logistic Regression and Random Forest compare on the same held-out test set?
Logistic Regression is a commonly used method for binary classification because it models the probability of an outcome based on predictor variables. Hosmer, Lemeshow, and Sturdivant provide a statistical foundation for applying logistic regression to binary outcomes [1].
Random Forest provides a different approach by combining multiple decision trees into an ensemble. Breiman introduced Random Forest as an ensemble method for classification and regression problems [2].
The scikit-learn library provides implementations of these machine learning methods as well as preprocessing and evaluation tools used in this experiment [3].
Based on these approaches, this study compares Logistic Regression and Random Forest using the same cleaned dataset and held-out test set.
## 2. Methodology
### 2.1 Dataset
The experiment uses the Titanic passenger dataset associated with the Kaggle Titanic Machine Learning from Disaster competition.
The dataset contains 891 passenger records and 12 original columns.
The target variable is:
```text
Survived
```
where:
```text
0 = Did not survive
1 = Survived
```
### 2.2 Features
The main features used in the experiment include:
* `Pclass`
* `Sex`
* `Age`
* `SibSp`
* `Parch`
* `Fare`
* `Embarked`
A family-related feature called `FamilySize` was also created.
### 2.3 Data Cleaning
Missing `Age` values were replaced using the median age. Missing `Embarked` values were replaced using the mode.
The following columns were removed:
* `PassengerId`
* `Name`
* `Ticket`
* `Cabin`
Categorical variables were converted into numerical variables using one-hot encoding.
### 2.4 Feature Engineering
The following feature was created:
```text
FamilySize = SibSp + Parch + 1
```
This represents the number of family members travelling with each passenger, including the passenger.
### 2.5 Models
Two classification models were used.
#### Logistic Regression
Logistic Regression was used as a baseline binary classification model.
#### Random Forest
Random Forest was used as a tree-based ensemble classification model.
### 2.6 Evaluation Metrics
The models were evaluated using:
* Accuracy
* Precision
* Recall
* F1-score
Both models were evaluated on the same held-out test set.
## 3. Results
### 3.1 Model Performance
Replace the values below with the exact results obtained from the Google Colab experiment.
| Model               |   Accuracy |  Precision |     Recall |   F1-score |
| ------------------- | ---------: | ---------: | ---------: | ---------: |
| Logistic Regression | **INSERT** | **INSERT** | **INSERT** | **INSERT** |
| Random Forest       | **INSERT** | **INSERT** | **INSERT** | **INSERT** |
**Table 1.** Performance comparison of Logistic Regression and Random Forest.
### 3.4 Results Summary
The results show the performance of both models across four classification metrics. Accuracy provides the overall proportion of correct predictions, while Precision and Recall provide information about the types of classification performance related to the survival class. F1-score provides a combined measure of Precision and Recall.
The exact model comparison should be interpreted using the values reported in Table 1.
## 4. Discussion
This experiment compared Logistic Regression and Random Forest for predicting Titanic passenger survival. The two models represent different machine learning approaches. Logistic Regression provides a relatively simple linear classification framework, while Random Forest uses multiple decision trees to capture more complex relationships.
The engineered `FamilySize` feature combines `SibSp` and `Parch` into one family-related variable. This provides the models with an additional representation of family circumstances that may be useful for survival prediction.
The results should be interpreted using multiple metrics rather than accuracy alone. Differences between Precision and Recall can indicate that the models make different types of classification errors. The confusion matrix provides additional information about correct and incorrect predictions.
## 5. Limitations
This study has several limitations.
First, the dataset represents one historical event and a specific passenger population. Therefore, the findings cannot automatically be generalized to other populations or situations.
Second, the dataset contains missing information, particularly in the `Cabin` variable.
Third, only two machine learning models were evaluated. Other algorithms could produce different results.
Finally, the experiment uses a single train-test split. Cross-validation could provide a more stable estimate of model performance.
## 6. Conclusion
This study investigated whether passenger characteristics and engineered family-related features can be used to predict Titanic survival. Logistic Regression and Random Forest were trained using the same cleaned dataset and evaluated on the same held-out test set using Accuracy, Precision, Recall, and F1-score. The experiment demonstrates a complete machine learning workflow involving data cleaning, feature engineering, model training, and evaluation. Future work could use cross-validation, additional feature engineering, hyperparameter tuning, and additional classification algorithms to further investigate Titanic survival prediction.
## References
1. Hosmer DW, Lemeshow S, Sturdivant RX. 
2. Breiman L. Random forests.

