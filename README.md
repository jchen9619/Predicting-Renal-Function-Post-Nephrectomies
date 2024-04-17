![MAYBE A PHOTO](https://github.com/jchen9619/Predicting-Renal-Function-Post-Nephrectomies/blob/main/images/DALL%C2%B7E%202024-04-15%2022.42.18%20-%20A%20wide%2C%20flat%20design%20digital%20illustration%20depicting%20the%20theme%20of%20kidney%20health%20research%2C%20specifically%20focusing%20on%20'Predicting%20Renal%20Function%20Post%20Nephr.webp)
Image generated by DALL·E

# Predicting Renal Function Post Nephrectomy for Renal Masses
**Chen Chen, Siri Desiraju, Anna Dominic, Julia Manasson** <br>
[📊 Report](https://github.com/jchen9619/Predicting-Renal-Function-Post-Nephrectomies/blob/main/reports/Capstone_Final_Report.pdf)<br>
[🖼️ Poster](https://github.com/jchen9619/Predicting-Renal-Function-Post-Nephrectomies/blob/main/reports/vFCapstone_poster_group_9.pdf)

## Table of Contents
- [Project Overview](#Project-Overview)
- [Data](#data) 
- [Building Patient Cohorts](#building-patient-cohorts)
- [Rule-based Classification of Nephrectomies](#Rule-based-Classification-of-Nephrectomies)  
- [Additional Features: Demographics and Comorbidities](#Additional-Features-Demographics-and-Comorbidities)
- [Modeling](#modeling)
- [Tech Stack](#tech-stack)

## Project Overview
Kidneys perform critical functions including waste filtration, drug metabolism, and blood pressure regulation. Renal function can be impaired by conditions like renal masses, which are often malignant; in 2023, there were 81,800 new cases and 14,890 deaths from kidney cancer in the U.S. The treatment of renal masses varies based on factors like age and tumor type, with options including partial nephrectomy (PN) and radical nephrectomy (RN). PN aims to preserve kidney tissue but involves longer surgeries and potentially more complications than RN, which removes the entire kidney. Given the kidneys' vital roles, accurately predicting postoperative renal function is crucial for selecting the best treatment approach. In this study, we introduce a predictive model that uses preoperative patient characteristics and surgical intervention type to forecast short-term postoperative renal function. The model, developed using data from NYU Langone Health's electronic health records, focused on predominantly white male patients aged 50-70 years with common comorbidities like hypertension and diabetes. After extensive preprocessing, our approach utilized Multiple Linear Regression and XGBoost techniques, achieving a mean absolute percentage error of approximately 18-23%. With further refinement, this tool could guide treatment strategy selection by predicting kidney functions measured by estimated glomerular filtration rate (eGFR) or serum creatinine (Cr) two weeks after surgery.

## Data
The data were obtained from NYU Langone Health (NYULH) patient EHR records between the years 2011 and 2023. SQL was used to extract the various features from a remote data lake as demonstrated below:<br>
[SQL Code for EHR Extraction]()
![features](https://github.com/jchen9619/Predicting-Renal-Function-Post-Nephrectomies/blob/main/images/features.webp)

## Building Patient Cohorts
We used structured and unstructured electronic health record (EHR) data to construct a model that predicts eGFR and Cr two weeks post-surgery, with respective sample sizes of 705 and 764 patients. This entails an extensive filtering process as demonstrated below. 
![Uploading image.png…](https://github.com/jchen9619/Predicting-Renal-Function-Post-Nephrectomies/blob/main/images/capstone%20flowchart%20(1)%20(1).png)

The baseline characteristics of patients in the the eGFR and Cr cohorts are shown in Table 1. In both cohorts, the patients were predominantly male, white, and overweight. Approximately 60% had HTN, 25-30% had DM, and 40-50% reported tobacco use.
![](https://github.com/jchen9619/Predicting-Renal-Function-Post-Nephrectomies/blob/main/images/baseline.jpg)<br>
[ADD CODE]

## Rule-based Classification of Nephrectomies
For many patients the type of nephrectomy procedure was not specified or incorrectly specified in the extracted procedure name. We therefore relied on free-form text within pathology reports to generate procedure type classifications whenever possible. First, we excluded pathology reports not associated with nephrectomies (e.g., biopsies, non-renal procedures). Next, we generated key words that were specifically associated with RN (e.g., ‘ureter’, ‘radical’, ‘total’) or PN (‘inked’, ‘partial’), and used them to classify the procedures. For individuals without corresponding pathology reports, we used the procedure name when it differentiated between partial or radical nephrectomy, having found it to be accurate in the majority of cases that were cross-referenced with pathology reports (match rates of 86% for PN and 95% for RN). Patients for whom we could not ascertain the type of nephrectomy by pathology report or procedure name were excluded. Patients with transplant kidneys or multiple nephrectomies were also excluded. <br> 
[ADD CODE]

## Modeling
To predict postoperative renal function, we employed both Linear Regression and XGBoost models. These models, exploring linear and non-linear relationships in demographic and clinical variables, offered insights into feature contributions. We chose MAPE (Mean Absolute Percentage Error) for its scale- independence and interpretability, as it suits the clinical context of renal failure prediction and offers a clear, understandable measure of accuracy. <br>
[ADD CODE]

## Results
The XGBoost models outperformed the Multiple Linear Regression models, and notably, the Cre- atinine cohort exhibited superior results compared to the GFR cohort, possibly attributed to the larger sample size within the former. Intriguingly, following Recursive Feature Elimination, the optimal model for the Creatinine cohort identified key features, including ’bmi’, ’pre creat’, ’pn ind’, and ’race White’. In contrast, the GFR model retained all features, excluding certain race indicators. Moreover, the models demonstrated enhanced performance within the Caucasian demographic, potentially reflecting the predominant Caucasian composition of NYU Langone patients.
![](https://github.com/jchen9619/Predicting-Renal-Function-Post-Nephrectomies/blob/main/images/results.jpg)

## Tech Stack
- Python
- SQL

