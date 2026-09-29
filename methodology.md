# Methodology
## 1. Research Question
Can passenger characteristics and engineered family-related features be used to predict Titanic survival, and how do Logistic Regression and Random Forest compare on the same held-out test set?
## 2. Dataset Description
The experiment uses the public Titanic passenger dataset associated with the Kaggle Titanic Machine Learning from Disaster competition.
The dataset contains:
* **Rows:** 891
* **Columns:** 12
* **Target:** `Survived`
* **Problem Type:** Binary Classification
The target variable `Survived` indicates whether a passenger survived the Titanic disaster.
* `0` = Did not survive
* `1` = Survived
## 3. Features
The main predictive features are:
* `Pclass`
* `Sex`
* `Age`
* `SibSp`
* `Parch`
* `Fare`
* `Embarked`
A new feature called `FamilySize` was also created.
## 4. Missing Values
The dataset contains missing values, particularly in the `Age`, `Cabin`, and `Embarked` columns.
The following strategies were used:
* Missing `Age` values were replaced using the median age.
* Missing `Embarked` values were replaced using the most frequent value.
* `Cabin` was removed because it contains a large amount of missing information.
## 5. Data Cleaning
The following columns were removed:
* `PassengerId`
* `Name`
* `Ticket`
* `Cabin`
These columns were not used as direct predictive features in the experiment.
Categorical variables such as `Sex` and `Embarked` were converted into numerical variables using one-hot encoding.
## 6. Feature Engineering
A family-related feature was created using `SibSp` and `Parch`.
The formula is:
```text
FamilySize = SibSp + Parch + 1
```
This feature represents the total number of family members travelling with a passenger, including the passenger.
## 7. Train-Test Split
The dataset was divided into training and testing sets.
The experiment used:
```text
Test size = 30%
Random state = 42
```
Stratified splitting was used to maintain the distribution of the target variable.
## 8. Machine Learning Models
Two classification models were selected.
### Logistic Regression
Logistic Regression was used as a baseline model for binary classification. It estimates the probability of belonging to a class and provides a relatively simple and interpretable classification approach.
### Random Forest
Random Forest was selected as a tree-based ensemble model. It combines multiple decision trees and can capture non-linear relationships between features.
## 9. Feature Scaling
StandardScaler was used for the Logistic Regression model.
The scaler was fitted on the training data and then applied to the test data.
Random Forest was trained using the original numerical feature values because tree-based models generally do not require feature scaling.
## 10. Evaluation Metrics
The models were evaluated using four metrics.
### Accuracy
Accuracy measures the proportion of all predictions that are correct.
### Precision
Precision measures how many of the passengers predicted as survivors were actually survivors.
### F1-score
F1-core is the harmonic mean of Precision and Recall.
Using multiple metrics provides a more complete evaluation than using accuracy alone.
## 11. Limitations
The study has several limitations.
First, the dataset represents a single historical event and a specific passenger population. Therefore, the findings cannot automatically be generalized to other situations.
Second, the dataset contains missing information, particularly for passenger cabin information.
Third, only two machine learning models were tested.
Finally, the experiment uses a single train-test split. Model performance could vary with a different split or with cross-validation.
