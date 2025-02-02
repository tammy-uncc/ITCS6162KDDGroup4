# ITCS 6162 KDD Group 4
Welcome to the repository for Group 4 project documentation

## Github repository
https://github.com/tammy-uncc/ITCS6162KDDGroup4.git


## Introduction
Group 4 decided they would like to research whether an individual could change their lifestyle factors in time to reduce or eliminate the onset of Alzheimer's. For example, suppose an individual knew that a healthier diet could reduce their chance of a positive diagnosis. In that case, they may prioritize eating healthier earlier in their lives. This dataset includes many lifestyle factors (BMI, smoking status, alcohol consumption, physical activity, diet quality, and sleep quality) that will help build predictive and prescriptive objectives.
We will be using supervised learning methods as the diagnosis of Alzheimer's is a known outcome in this dataset.

We will look into classification, clustering, and feature selection to identify and select the most relevant features to improve the predictive models. By using these approaches, group 4 hopes this research will uncover insights into lifestyle risk factors for developing Alzheimer's and which lifestyle factor modifications could mitigate those risks.

### The Group 4 Team
The team collaborated by meeting twice per week over Zoom. We also communicated extensively by email and SMS text. We delegated the tasks as a group and each performed our tasks alone or with others. Our work was then reviewed, and if necessary, added to by the others in the group. The choice of the research question was a group collaboration with each member providing one or more questions to the discussion. Once identified the team had a direction.  

#### Team Members
Following are the members of the group and the tasks they worked on:  

##### Julie Berryhill<br>
Julie wrote up the introduction and performed the work on the PyCaret code section of the notebook.

##### Gabriel Van Dreel<br>
Gabriel wrote up the data understanding section and performed the work on the preprocessing and modeling sections of the notebook.

##### Dasha Rizvanova<br>
Dasha wrote the conclusion and evaluation sections.

##### Manoj Aitha<br>
Manoj investigated if there was any value in performing the association rules on our dataset given our research question.

##### Tammy Ziegler<br>
Tammy led the meetings and kept the meeting notes. She also built out the initial notebook document with the data loading and performed the initial work on the exploratory data analysis.


### Problem Understanding
The problem starts with the question: Are there any lifestyle factors that could be changed to reduce or eliminate the onset of Alzheimer's? It is one thing to be able to identify if someone can be diagnosed with Alzheimer's but quite the other to understand what we can do to prevent or even delay the onset of the disease. We consider lifestyle factors to be those things we can change, such as BMI, Smoking, Alcohol Consumption, Physical Activity, Diet Quality, and Sleep Quality. We could also include things such as cholesterol, but they are typically the result of a quality diet.

#### Relevant Domain
We provided some links for further reading.

https://www.cdc.gov/aging/publications/features/lower-your-dementia-risk/index.html

https://www.medicalnewstoday.com/articles/4-lifestyle-changes-may-improve-cognitive-function-slow-alzheimers

https://edition.cnn.com/2024/06/07/health/alzheimers-dementia-ornish-lifestyle-wellness/index.html

https://www.kaggle.com/datasets/rabieelkharoua/alzheimers-disease-dataset?resource=download


## Data Understanding
https://www.kaggle.com/datasets/rabieelkharoua/alzheimers-disease-dataset?select=alzheimers_disease_data.csv

We will attempt to use the Alzheimer's data pointed to by the link above for our research. The dataset consists of 2,150 entries detailing various physiological characteristics of patients. These patients were considered for an Alzheimer's disease diagnosis and whether they were formally diagnosed with the illness. Some data, such as the gender, and ethnicity columns are categorical. Other data is numeric and represents either an index for a rating of some condition, such as sleep quality, or a direct measurement of some physical characteristic, such as cholesterol. All the numeric data points could be considered time series data concerning age. However, some columns in the dataset, such as the name of the doctor in charge of a given patient, have been sanitized and provide no meaningful information.


#### The Features
There are 33 features in the dataset.  Six features are Lifestyle features. These are listed below, followed by the other features. The list was taken directly from the data sources web page and reordered to represent our focus.

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
- EducationLevel: The education level of the patients, is coded as follows:
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

#### The Diagnosis:
- Diagnosis: Diagnosis status for Alzheimer's Disease, where 0 indicates No and 1 indicates Yes.

### Data analysis
Our analysis of the data involved various visualizations and statistics gathering. We used the `yada_profiling` tool to build a basic understanding of the data. We learned that there are no duplicate rows or rows with missing data, so we will not need to impute any data or remove rows. However, we noticed that the label classification, Diagnosis, is heavily weighted with a negative diagnosis. There are twice as many negative diagnoses as there are positive. Hence, this could cause the prediction models to have a bias. In addition, we noticed the Ethnicity and Education Level, as well as many of the binary class features, are also imbalanced. 

We then performed different visualizations. A heatmap shows that only five features have some semblance of a correlation with the Diagnosis: MMSE, FunctionalAssessment, ADL, MemoryComplaints, and BehavioralProblems. None of the features are correlated with one another. Density plots were used to help identify any relationships between the numeric features and the label. They identify the same numeric features as the heatmap as the most significant. On the categorical data, we used annotated bar plots to show the distribution of the categories concerning the diagnosis. The plots were annotated with the diagnosis percent for each category. The only two features to show an imbalance were MemoryComplaints and BehaviorProblems, confirming with the heatmap that they are the most significant categorical features. 

Finally, since we are concerned about lifestyle choices impacting the onset of Alzheimer's, we produced swarm plots to show if any relationship exists between the numeric lifestyle choices with Gender and Ethnicity. Gender and Ethnicity were chosen as these are features a patient cannot control. It appears that there are no significant correlations; however, a keen observer might see that Asians who drink a lot may be more likely to develop Alzheimer's. This observation needs to be tempered with the fact that 40.78% of Asians are positive for Alzheimer's, which is the highest of all the ethnic groups covered and much more than the total dataset of 36%.


## Data Preparation
The categorical columns of the Alzheimer's Disease Dataset will be one-hot encoded during data preprocessing. Any numeric columns found to be normally distributed will be standardized to reflect a normal distribution. Others could be linearly scaled to reduce the effect of bias in any machine learning models for the dataset. The sanitized columns in the dataset could also be dropped since they provide no useful information.

The Patient ID and the Doctor in Charge have been removed from the dataset before processing. These features provide little to no value to our study. Patient ID is a numeric identifier and is unrelated to the data. DoctorInCharge has been given to us sanitized and contains no valuable information. 


## Methodology
A grid search was performed to tune hyperparameters for Logistic Regression and Random Forest Classifier models. These were each selected for their ability to effectively fit a non-linear decision boundary with high generalizability.

Although the Random Forest Classifier model has the limitation of having only orthogonal decision boundaries, it was observed to perform binary classification for whether a given patient had Alzheimer's with the highest accuracy. Each model was analyzed using several evaluation criteria. Confusion matrices and metrics for precision, recall, and f1-score were evaluated for both the Logistic Regression model and the Random Forest Classifier model. It was observed that the logistic regression model had a more balanced confusion matrix for misclassifications and, in one instance, higher recall than the random forest classifier concerning each classification category.

Additionally, we leveraged the PyCaret module to validate prediction performance on several other models. We performed experiments with the original untreated data (without the PatientID and DoctorInCharge features), the one-hot encoded data, and the one-hot encoded data after it was over-sampled to balance the target label. A 20% validation set was removed from the data before being balanced and used in the PyCaret module.

The experiments show that the one-hot encoded and rebalanced data derives the best predictions in terms of accuracy using either the Random Forest Classifier or Extra Tees Classifier depending on the run.

Finally, we reran the Random Forest Classifier using the one-hot encoding. We also split the data to obtain a test and validation set to use after training. In both cases on the test and validation, the model performed with an accuracy of 93% (some runs may vary).

### Evaluation

The data shows that the strongest predictors were MMSE, Functional Assessment, and ADL. This does not mean that lifestyle features do not play a role. Diet Quality and its components, such as Cholesterol Triglycerides, Diabetes do have some say in the matter even if it is relatively small. It seems smokers are not any more likely to be at risk of Alzheimer's than non-smokers. Physical activity also rated low, showing that it likely has little influence on the prediction.

The data appears to counter other studies and research. This is likely due to the quality of the data.  For one, it is a small dataset, and we do not know much about its source or how and when it was derived.  There are 32 features and the combinations are enormous. Much larger than the 2,150 record dataset we used for the study. Also, this data is a static picture of time. A study like this may perform better with time series data on a patient for many patients over several years.  It would be useful to know what patients were doing to cause or prevent the disease in the future. Additionally, the imbalance in certain features, such as Ethnicity could skew the results, highlighting the need for a more balanced dataset. 

## Conclusion
We have decided to work with the Alzheimer's Disease Dataset, which contains health information about 2,149 patients. This dataset includes patient demographics, lifestyle factors, medical history, clinical measurements, cognitive and functional assessments, symptoms, diagnosis data, and confidential information. Our research question focused on investigating whether lifestyle factors play a role in developing Alzheimer's disease and whether modifying these factors can reduce the risk of getting the disease.

Several models were implemented, including; Logistic Regression and Random Forest Classifier. The Logistic Regression model achieved an overall accuracy of approximately 83%, with a precision of 85% for class 0 and 80% for class 1. As for the Random Forest Classifier, after rebalancing the data it achieved an overall accuracy of around 93%, with the precision of 93% for class 0 and 94% for class 1 on the validation data. 

We used feature selection with SelectKBest to extract the most relevant features based on their chi-square scores, indicating their importance in predicting Alzheimer's disease. We found only four out of six lifestyle factors; BMI, Physical Activity, Diet Quality, and Sleep Quality scored as average predictors of Alzheimer's disease. The other two were insignificant.

Ultimately, the data and this study were not able to corroborate that lifestyle changes can significantly alter the outcome of an Alzheimer's disease diagnosis.



## Citations
@misc{rabie_el_kharoua_2024,
title={Alzheimer's Disease Dataset},
url={https://www.kaggle.com/dsv/8668279},
DOI={10.34740/KAGGLE/DSV/8668279},
publisher={Kaggle},
author={Rabie El Kharoua},
year={2024}
}
