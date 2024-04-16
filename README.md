![MAYBE A PHOTO](https://github.com/jchen9619/Predicting-Renal-Function-Post-Nephrectomies/blob/main/images/DALL%C2%B7E%202024-04-15%2022.42.18%20-%20A%20wide%2C%20flat%20design%20digital%20illustration%20depicting%20the%20theme%20of%20kidney%20health%20research%2C%20specifically%20focusing%20on%20'Predicting%20Renal%20Function%20Post%20Nephr.webp)
# Predicting Renal Function Post Nephrectomy for Renal Masses
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
Kidneys perform critical functions including waste filtration, drug metabolism, and blood pressure regulation. Renal function can be impaired by conditions like renal masses, which are often malignant; in 2023, there were 81,800 new cases and 14,890 deaths from kidney cancer in the U.S. The treatment of renal masses varies based on factors like age and tumor type, with options including partial nephrectomy (PN) and radical nephrectomy (RN). PN aims to preserve kidney tissue but involves longer surgeries and potentially more complications than RN, which removes the entire kidney. Given the kidneys' vital roles, accurately predicting postoperative renal function is crucial for selecting the best treatment approach. In this study, we introduce a predictive model that uses preoperative patient characteristics and surgical intervention type to forecast short-term postoperative renal function. The model, developed using data from NYU Langone Health's electronic health records, focused on predominantly white male patients aged 50-70 years with common comorbidities like hypertension and diabetes. After extensive preprocessing, our approach utilized Multiple Linear Regression and XGBoost techniques, achieving a mean absolute percentage error of approximately 18-23%. With further refinement, this tool could guide treatment strategy selection by predicting kidney functions measured by eGFR and creatinine two weeks after surgery.

## Data
The data were obtained from NYU Langone Health (NYULH) patient EHR records between the years 2011 and 2023. SQL was used to extract the various features from a remote data lake as demonstrated below:
[features](https://github.com/jchen9619/Predicting-Renal-Function-Post-Nephrectomies/blob/main/images/features.webp)


## Building Patient Cohorts
Creating a reliable cohort for our analysis involved intricate decisions and meticulous steps. One pivotal aspect was defining the postoperative timeframe for the GFR cohort. Experimenting with various periods, we settled on a two-week interval, supported by a robust sample size of 549 patients and aligning with the clinical expectation of recovery stability within this timeframe.


## Rule-based Classification of Nephrectomies
[(Back to top)](#table-of-contents)
dfsjkld;ajdklf;ad

## Additional Features: Demographics and Comorbidities
[(Back to top)](#table-of-contents)
dfsjkld;ajdklf;ad

## Modeling
[(Back to top)](#table-of-contents)
dfsjkld;ajdklf;ad

## Tech Stack
[(Back to top)](#table-of-contents)
dfsjkld;ajdklf;ad
