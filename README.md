# Refer to KDD_Project.ipynb for Deliverable 1 & 2


# ITCS 6162 KDD Group 4
Repository for group project documentation

## Github repository
https://github.com/tammy-uncc/ITCS6162KDDGroup4.git


## Introduction
Group 4 decided they would like to research whether an individual could change their lifestyle factors in time to reduce or eliminate the onset of Alzheimer's. For example, if an individual knew that a healthier diet could reduce their chance of a positive diagnosis, then they may put eating healthier as an earlier priority in their lives. This dataset includes many lifestyle factors (BMI, smoking status, alcohol consumption, physical activity, diet quality, and sleep quality) that will help in building predictive and prescriptive objectives.
We will be using supervised learning methods as the diagnosis of Alzheimer's is a known outcome in this dataset.

We will be looking into classification, clustering, and feature selection to identify and select the most relevant features to improve the predictive models. By using these approaches, group 4 hopes this research will uncover any insights of lifestyle risk factors for developing Alzheimer's and which lifestyle factor modifications could mitigate those risks.

### The Group 4 Team
The team collaborated by meeting twice per week over Zoom. We also communicated extensively by email and SMS text. We delegated the tasks as a group and each one of us performed our tasks alone or with others. Our work was then reviewed, and if necessary, added to by the other members of the group. The choice of the research question was a group collaboration with each member providing one or more questions to the discussion. Once identified the team had a direction.  

#### Team Members
Following are the members of the group and the tasks they worked on:  

##### Julie Berryhill<br>
Julie wrote up the introduction and performed the work on the PyCaret code section of the notebook.

##### Gabriel Van Dreel<br>
Gabriel wrote up the data understanding section and performed the work on the preprocessing coding and the modeling sections of the notebook.

##### Dasha Rizvanova<br>
Dasha wrote the conclusion and evaluation sections.

##### Manoj Aitha<br>
Manoj investigated if there was any value in performing the association rules on our dataset given our research question.

##### Tammy Ziegler<br>
Tammy lead the meetings and kept the meeting notes. She also built out the initial notebook document with the data loading and data analysis code.


### Problem Understanding
The problem starts with the question, are there any lifestyle factors that could be changed to reduce or eliminate the onset of Alzheimer's? It is one thing to be able to identify if someone can be diagnosed with Alzheimer's but quite the other to understand what we can do to prevent or even delay the onset of the disease. 

#### Relevant Domain
Here are some links relative to the topic.

https://www.cdc.gov/aging/publications/features/lower-your-dementia-risk/index.html

https://www.medicalnewstoday.com/articles/4-lifestyle-changes-may-improve-cognitive-function-slow-alzheimers

https://edition.cnn.com/2024/06/07/health/alzheimers-dementia-ornish-lifestyle-wellness/index.html

https://www.kaggle.com/datasets/rabieelkharoua/alzheimers-disease-dataset?resource=download


### Data Understanding
https://www.kaggle.com/datasets/rabieelkharoua/alzheimers-disease-dataset?select=alzheimers_disease_data.csv

We will attempt to use the above Alzheimer's data set for our research. The dataset consists of 2150 entries detailing various physiological characteristics of patients who were considered for an Alzheimer's disease diagnosis and whether they were formally diagnosed with the illness. Some of the data such as the gender and ethnicity columns is categorical while other data is numeric and represents either an index for a rating of some condition such as sleep quality or a direct measurement of some physical characteristic such as cholesterol. All the numeric data points could be considered time series data concerning age. Some columns in the dataset such as the name of the doctor in charge of a given patient, however, have been sanitized and provide no meaningful information.


#### The Features
There are 33 features in the dataset.  Six of the features are Lifestyle features.  These follow and the remainder of the features after that.  This was taken right from the data sources page and presented here in a different order to represent out purpose.

##### Lifestyle Features
- BMI: Body Mass Index of the patients, ranging from 15 to 40.
- Smoking: Smoking status, where 0 indicates No and 1 indicates Yes.
- AlcoholConsumption: Weekly alcohol consumption in units, ranging from 0 to 20.
- PhysicalActivity: Weekly physical activity in hours, ranging from 0 to 10.
- DietQuality: Diet quality score, ranging from 0 to 10.
- SleepQuality: Sleep quality score, ranging from 4 to 10.


##### Other Features
- PatientID: A unique identifier assigned to each patient (4751 to 6900).
- Age: The age of the patients ranges from 60 to 90 years.
- Gender: Gender of the patients, where 0 represents Male and 1 represents Female.
- Ethnicity: The ethnicity of the patients, coded as follows:
  - 0: Caucasian
  - 1: African American
  - 2: Asian
  - 3: Other
- EducationLevel: The education level of the patients, coded as follows:
  - 0: None
  - 1: High School
  - 2: Bachelor's
  - 3: Higher
- FamilyHistoryAlzheimers: Family history of Alzheimer's Disease, where 0 indicates No and 1 indicates Yes.
- CardiovascularDisease: Presence of cardiovascular disease, where 0 indicates No and 1 indicates Yes.
- Diabetes: Presence of diabetes, where 0 indicates No and 1 indicates Yes.
- Depression: Presence of depression, where 0 indicates No and 1 indicates Yes.
- HeadInjury: History of head injury, where 0 indicates No and 1 indicates Yes.
- Hypertension: Presence of hypertension, where 0 indicates No and 1 indicates Yes.
- SystolicBP: Systolic blood pressure, ranging from 90 to 180 mmHg.
- DiastolicBP: Diastolic blood pressure, ranging from 60 to 120 mmHg.
- CholesterolTotal: Total cholesterol levels, ranging from 150 to 300 mg/dL.
- CholesterolLDL: Low-density lipoprotein cholesterol levels, ranging from 50 to 200 mg/dL.
- CholesterolHDL: High-density lipoprotein cholesterol levels, ranging from 20 to 100 mg/dL.
- CholesterolTriglycerides: Triglycerides levels, ranging from 50 to 400 mg/dL.
- Cognitive and Functional Assessments
- MMSE: Mini-Mental State Examination score, ranging from 0 to 30. Lower scores indicate cognitive impairment.
- FunctionalAssessment: Functional assessment score, ranging from 0 to 10. Lower scores indicate greater impairment.
- MemoryComplaints: Presence of memory complaints, where 0 indicates No and 1 indicates Yes.
- BehavioralProblems: Presence of behavioral problems, where 0 indicates No and 1 indicates Yes.
- ADL: Activities of Daily Living score, ranging from 0 to 10. Lower scores indicate greater impairment.
- Confusion: Presence of confusion, where 0 indicates No and 1 indicates Yes.
- Disorientation: Presence of disorientation, where 0 indicates No and 1 indicates Yes.
- PersonalityChanges: Presence of personality changes, where 0 indicates No and 1 indicates Yes.
- DifficultyCompletingTasks: Presence of difficulty completing tasks, where 0 indicates No and 1 indicates Yes.
- Forgetfulness: Presence of forgetfulness, where 0 indicates No and 1 indicates Yes.
- DoctorInCharge: This column contains confidential information about the doctor in charge, with "XXXConfid" as the value for all patients.

#### The Diagnosis
- Diagnosis: Diagnosis status for Alzheimer's Disease, where 0 indicates No and 1 indicates Yes.

### Data analysis
Our analysis of the data involved various visualizations and statistics gathering. We used the yada_profiling tool to build a basic review of the data. We learned that there are no duplicate rows or rows with missing data. As such we will not need to impute any data or remove rows. However, we noticed that the label classification, Diagnosis, is heavily weighted with a negative diagnosis. There are twice as many negative diagnoses as there are positive. This could cause the prediction models to have a bias.  

In addition, we noticed the Ethnicity and Education Level are also imbalanced as well as many of the binary class features. The "Education Level" does not appear to provide any value. Hence we decided to remove it from the dataset. 

We then performed visualizations. A heatmap shows that only five features have some semblance of a correlation with the Diagnosis; MMSE, FunctionalAssessment, ADL, MemoryComplaints, and BehavioralProblems. None of the features are correlated with one another. Density plots were used to help identify any relationships between the numeric features and the label. They identify the same numeric features as the heatmap as the most significant. On the categorical data, we used annotated bar plots to show the distribution of the categories concerning the diagnosis. The only two features to show an imbalance were MemoryComplaints and BehaviorProblems, confirming with the heatmap that they are the most significant categorical features. 

Finally, since we are concerned about lifestyle choices having an impact on the onset of Alzheimer's we produced swarm plots to show if any relationship exists between the numeric lifestyle choices with Gender and Ethnicity. Gender and Ethnicity were chosen as these are features a patient cannot control. It appears that there are no significant correlations however, a keen observer might see that Asians who drink a lot may be more likely to develop Alzheimer's, but that needs to be tempered with the fact that 40.78% of Asians are positive for Alzheimer's, which is the highest of all the Ethnic groups covered. It is also much more than the total dataset of 36%.


## Data Preprocessing
The categorical columns of the Alzheimer's Disease Dataset will be one-hot encoded during data preprocessing. Any of the numeric columns will be standardized such that they reflect a normal distribution if they are found to be normally distributed while others could be linearly scaled to reduce the effect of bias in any machine learning models for the dataset. The sanitized columns in the dataset could also be dropped since they provide no useful information.

We decided to drop the Education Level feature as well as the Patient ID and the Doctor in Charge. These features provide little to no value to our study. Patient ID is a numeric identifier and is unrelated to the data. DoctorInCharge has been given to us sanitized and contains no valuable information. Education Level has about the same diagnosis split as the entire set.


## Methodology
A grid search was performed to tune hyperparameters for a logistic regression model and a random forest classifier model that were each selected for their ability to effectively fit a non-linear decision boundary with high generalizability.

Although the random forest classifier model has the limitation of having only orthogonal decision boundaries, it was observed to perform binary classification for whether a given patient had Alzheimer's with the highest accuracy. Each model was analyzed with several evaluation criteria where confusion matrices and metrics for precision, recall, and f1-score were evaluated for both the logistic regression model and the random forest classifier model. It was observed that the logistic regression had a more balanced confusion matrix for misclassifications and therefore had a more stable and, in one instance, higher recall than the random forest classifier concerning each classification category.

Additionally, we leveraged the PyCaret module to validate prediction performance on a host of models.  We performed experiments with the original untreated data (without the Patient ID and Doctor in Charge features), the one hot encoded data, and the one hot encoded data after it was over-sampled to balance the target label.

The experiments show that the one-hot encoded and rebalanced data derives the best predictions in terms of accuracy using an Extra trees Classifier.

Finally, we redid the RandomForestClassifier using the one-hot encoding. We also split the data to obtain a test and validation set to use after training. In both cases on the test and validation the model performed with an accuracy of 93% (some runs may vary).

### Evaluation

For the k=10 best features, univariate statistical tests were performed for the predictive relationship between the input features and class labels used with the trained models. A score representing a proportion of predictive contribution with respect to the 10th-most influential feature to performing accurate classification was generated and sorted in descending order based on a fit to the distribution of data points in each column to a chi squared distribution. It was observed that MMSE, FunctionalAssessment, and ADL were the strongest predictors of an Alzheimer's classification. 

## Conclusion
We have decided to work with the Alzheimer's Disease Dataset, which contains health information about 2,149 patients. This dataset includes patient demographics, lifestyle factors, medical history, clinical measurements, cognitive and functional assessments, symptoms, diagnosis data, and confidential information.

Our research question focused on investigating whether lifestyle factors play a role in developing Alzheimer's disease and whether modifying these factors can reduce the risk of getting the disease.

We dropped some columns, such as PatientID and DoctorInCharge, as they were irrelevant to our research question. We used feature selection with SelectKBest to extract the most relevant features based on their chi-square scores, indicating their importance in predicting Alzheimer's disease. We found that four out of six lifestyle factors—BMI, Physical Activity, Diet Quality, and Sleep Quality—are among the top predictors of Alzheimer's disease.

We implemented two models, Logistic Regression and Random Forest Classifier. The Logistic Regression model achieved an overall accuracy of approximately 83%, with the precision of 85% for class 0 and 80% for class 1. As for the Random Forest Classifier, it achieved an overall accuracy of around 85%, with the precision of 82% for class 0 and 95% for class 1. Although the Random Forest Classifier performed better, both models require further tuning to improve their performance.

## Citations
@misc{rabie_el_kharoua_2024,
title={Alzheimer's Disease Dataset},
url={https://www.kaggle.com/dsv/8668279},
DOI={10.34740/KAGGLE/DSV/8668279},
publisher={Kaggle},
author={Rabie El Kharoua},
year={2024}
}
