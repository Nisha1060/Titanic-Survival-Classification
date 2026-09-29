# Titanic-Survival-Classification
## Project Overview
This project investigates whether passenger characteristics and engineered family-related features can be used to predict Titanic survival.
The study compares two machine learning classification models:
* Logistic Regression
* Random Forest
Both models are evaluated using the same held-out test dataset.
## Research Question
**Can passenger characteristics and engineered family-related features be used to predict Titanic survival, and how do Logistic Regression and Random Forest compare on the same held-out test set?**
## Dataset
The project uses the Titanic passenger dataset associated with the Kaggle Titanic Machine Learning from Disaster competition.
* **Number of rows:** 891
* **Number of original columns:** 12
* **Target variable:** `Survived`
* **Problem type:** Binary Classification
### Main Features
* `Pclass`
* `Sex`
* `Age`
* `SibSp`
* `Parch`
* `Fare`
* `Embarked`
* `FamilySize`
### Target
`Survived`
* `0` = Did not survive
* `1` = Survived
## Data Preprocessing
The following preprocessing steps were performed:
1. Checked the dataset structure and missing values.
2. Removed unnecessary identifier and text columns.
3. Filled missing `Age` values using the median.
4. Filled missing `Embarked` values using the mode.
5. Created a new `FamilySize` feature.
6. Converted categorical variables into numerical features.
7. Split the data into training and testing sets.
## Feature Engineering
A family-related feature was created:
```text
FamilySize = SibSp + Parch + 1
```
This feature represents the total number of family members travelling with each passenger, including the passenger.
## Machine Learning Models
### 1. Logistic Regression
Logistic Regression was used as a baseline binary classification model.
### 2. Random Forest
Random Forest was used as a tree-based ensemble classification model.
## Evaluation Metrics
The models were evaluated using:
* Accuracy
* Precision
* Recall
* F1-score
## Results
The model results are reported in the research paper and experiment notebook.
| Model               |  Accuracy | Precision |    Recall |  F1-score |
| ------------------- | --------: | --------: | --------: | --------: |
| Logistic Regression | See paper | See paper | See paper | See paper |
| Random Forest       | See paper | See paper | See paper | See paper |
## Project Files
### Research Paper
[Read the Research Paper](paper.md)
### Experiment Notebook
[Open the Experiment Notebook](experiment.ipynb)
### Methodology
[Read the Methodology](methodology.md)
### Literature Review
[Read the Literature Review](literature_review.md)
### Model Results
[View Model Results](model_results.csv)
## Limitations
This study has several limitations:
* The dataset represents one historical event.
* The dataset is relatively small.
* Some passenger information contains missing values.
* Only two machine learning models were evaluated.
* The experiment uses a single train-test split.
## Conclusion
This project demonstrates how passenger characteristics and family-related features can be used for Titanic survival classification. Logistic Regression and Random Forest were trained and evaluated using the same test dataset and multiple classification metrics.
## Technologies Used
* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn
* Google Colab
* GitHub
