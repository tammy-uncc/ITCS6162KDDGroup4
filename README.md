# ITCS 6162 KDD Group 4
Repository for group project documentation

## Github repository
https://github.com/tammy-uncc/ITCS6162KDDGroup4.git

## Team Members
Julie Berryhill<br>
Manoj Aitha<br>
Gabriel Van Dreel<br>
Tammy Ziegler<br>
Dasha Rizvanova<br>


## Introduction of Project
Group 4 decided that they would like to research the possibility of whether an individual could change their lifestyle factors in time to reduce or eliminate the onset of Alzheimer's. For example, if an individual knew that a healthier diet could reduce their chance of a positive diagnosis, then they may put eating healthier as an earlier priority in their lives. This dataset includes many lifestyle factors (BMI, smoking status, alcohol consumption, physical activity, diet quality, and sleep quality) that will help in building predictive and prescriptive objectives. 
We will be using supervised learning methods as the diagnosis of Alzheimer's is a known outcome in this dataset. We will be looking into classification, clustering, and feature selection to identify and select the most relevant features to improve the predictive models. By using these approaches, group 4 hopes that this research will uncover any insights of lifestyle risk factors for developing Alzheimer’s and which lifestyle factor modifications could mitigate those risks.

### Problem Understanding
This analysis will focus on identifying the characteristics of people who are diagnosed with Alzhiemers disease. Blah blah blah

#### Research Questions
##### Tammy Questions
What characteristics are most common in people who become diagnosed with Alzheimer's disease?<br>
Which of the characteristics can be identified prior to the onset of the disease?<br>
https://www.nia.nih.gov/health/alzheimers-and-dementia/alzheimers-disease-fact-sheet
https://www.ncbi.nlm.nih.gov/pmc/articles/PMC8927715/

##### Dasha Questions
How do factors such as alcohol consumption, age, ethnic background, and medical history influence the risk of being diagnosed with Alzheimer's Disease? Most importantly, can we develop a model to identify individuals at risk based on these factors?
https://www.ncbi.nlm.nih.gov/pmc/articles/PMC10253673/
https://www.washingtonpost.com/wellness/2024/03/27/dementia-aging-risk-brain-diabetes-pollution-alcohol/
## Description of data

### Data Understanding

### Data Preparation
Data contains 1389 negative diagnosis and 760 with a positive diagnosis.

##### Data  
- Remvoe PatientId and DoctorInCharge
- Ethnicity.  As it is, the data is highly biased towards caucasions.  Perhaps remove.
- Education level.  Remvoe as this seems irrelavent.  
- Smoking ???.  Data is highly weighted to non-smokers. Look to see if there is a correlation
- Family history. Also highly weighted.  Look for a correlation.
- Medical History items all seem weighted to the negatives for each of the conditions specified.  Perhaps look for a correlation.
- Memory complaints and Behavioral Problems seems to be a very subjective data element.  Perhaps these should be removed.
- 


## Modeling

## Evaluation

## Conclusion

## Citations
@misc{rabie_el_kharoua_2024,
title={Alzheimer's Disease Dataset},
url={https://www.kaggle.com/dsv/8668279},
DOI={10.34740/KAGGLE/DSV/8668279},
publisher={Kaggle},
author={Rabie El Kharoua},
year={2024}
}
