# Covid19-Pakistan-InDepth-Analysis

### Note: Along with the python code another .ipynb file is added to directly view the running code instead of fitting the SVM. 

## Data Exploration Challenge:

### This is a project performing data analysis on the Corona Cases that were recorded from day 1 i.e 11 March to 25th April 2020.

The comparisons is made on even grounds that is each region despite of having different population had been compared and standardized to per million population. Since Punjab had a population of 119 Million and ICT had a population of 2 million in order to compare both regions in different metrics each metric was divided by million.

Libaries Used:

* Pandas
* Numpy
* SKlearn
* SVR (Support Vector Regressor)

## Data Cleansing:

* During Data Analysis it was found that different regions had different data recorded as KPTD had only data recorded from 11 March till 22 March so it was not included in the final verdict.
* The dates recorded were not in the same format, since the data had to be processed so each date was converted to same format using standardization.
* From 23rd April 2020 it was found that 2 Columns namely; Home Quarantine and Discharged had wrong data entered.

### Solution:
* Discharged column entries which were replaced with 2nd Home Quarantine column was corrected by replacing it with Recovered Column since the discharged patients were actually the patients that were recovered from the virus.
* Home Quarantine 1st column entries were replaced with Admitted Ventilator entries so in order to correct it, it was replaced with the Home Quarantine 2nd column which had same observations as of 1st column.


## Data Analysis:
Each region namely; Punjab, ICT, Sindh etc data was recorded separately by creating a DataFrame for each region.

Since different data was recorded on different dates, by that I mean that some column entries were not filled in the first few dates so in order to compare different regions each region was first compared with other by making different phases:

* Phase 1: 11 March - 22 March - Data of KPTD was recorded uptil this date
* Phase 2: 23 March - 28 March - Data recorded before data of Home Quarantin column.
* Phase 3: 29 March - 03 April - Data recorded before rest columns such as Admitted Critical, Ventilator and Foreign and Local Transmissions etc.
* Phase 4: 04 April - 11 April - Data recorded in a week.
* Phase 5: 11 April - 18 April - Data recorded in a week.
* Phase 6: 18 April - 25 April - Data recorded in a week.

Graphs of different regions in different phases are shown.
Graphs of different regions daily on different metric per million population are shown.

### Note:
Active Cases = Cumulative Tests positive - Discharged - Cumulative Expired

## Final Verdict:
AJK is the most successful, followed by Balochistan, then KP, then Punjab, then Sindh and atlast ICT the most struggling region.

The score is calculated by the following formula:
Score in first 24 days = (-( mean of first 24 days Active Cases / population per million) + (mean of first 24 Discharged Cases / pop per million) - (mean of deaths in first 24 days / population per million) ) * 0.52 (0.52 because 24/46 = 0.52)
Score in later 22 days = (- ( mean of later 22 days Active Cases / population per million) + (mean of later 22 Discharged Cases / pop per million) - (mean of deaths in later 22 days / population per million) + (mean of admitted stable cases / population per million) - (mean of admitted critical cases / population per million) ) * 0.48 (0.48 because 22/46 = 0.48)

### Total Score = Score in first 24 days + Score in later 22 days


 Cumulative Positive Cases Prediction in the next 10 days:

 The number of cumulative positive cases in the next 10 days were predicted using Support Vector Regressor.



