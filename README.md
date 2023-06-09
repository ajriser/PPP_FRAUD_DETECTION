# PPP_FRAUD_DETECTION
Analysis of PPP grants given and identifying probable frauds

### *Authors: Aayush Bakre, Ajanya Sharma*

### Table of Contents

- Problem Description
- Evaluation
- Dataset
- Setup Imports & Variables
- Exploring the Data

![alt text](https://gray-wafb-prod.cdn.arcpublishing.com/resizer/ELLb-0F79fu-eD2nA4_46JmkiJs=/1200x675/smart/filters:quality(85)/cloudfront-us-east-1.images.arcpublishing.com/gray/YT67CCYJY5FDNJDURKRAGZYETY.jpg)

### PPP Loan Fraud Detection

The Paycheck Protection Program (PPP) is a loan program by the U.S. government in 2020 to help certain businesses, self-employed workers, sole proprietors, nonprofit organizations, and tribal businesses keep paying their workers during the COVID-19 pandemic. PPP loans are private loans with low interest rates that can be used to cover payroll costs, rent, interest, and utilities. The loan amount is based on the average monthly payroll costs of the applicant,business type and can be forgiven if the business is unable to sustain duing the pandemic.The program is run by the U.S. Small Business Administration and the deadline to apply for a PPP loan was March 31, 2021.

The project is aimed at exploring loan data from the Paycheck Protection Program (PPP), which provided relief to small and medium-sized businesses during the COVID-19 pandemic. The primary objective is to create graphical visualizations of the data and apply anomaly detection methods to identify potentially fraudulent loans. The project outline suggests a few starting points, including reviewing PPP loan program eligibility criteria, downloading the full PPP loan dataset and NAICS codes data dictionary for businesses, summarizing the data through tabular summaries and graphical visualizations, investigating loans that have a high potential for fraud by grouping together loans in common categories and identifying outlier loans, and exploring the use of traditional unsupervised learning techniques such as anomaly detection.

## Dataset

The dataset with PPP data is sourced from the official SBA website which can be accessed using the following URL:
https://data.sba.gov/dataset/ppp-foia/resource/aab8e9f9-36d1-42e1-b3ba-e59c79f1d7f0?inner_span=True

The dataset with NAICS code is sourced from https://www.sba.gov/document/support-table-size-standards

Also geopandas .shp files have been used to plot state wise fraud in United States

## Evaluation

The dataset is a collection of entries on the PPP Loan Fraud application form. There is no training or a test dataset. Initial review doesn't point towards any strong correlations and predictors that would categorize the problem as a predictive or a dependence exerceise. At first glance, the dataset seems to be a good fit for unsupervised outlier detection methods just as the Project Brief suggests. 

## Approach to Analysis

In order to better understand the PPP Loan dataset, we investigated the data and performed initial exploratory analysis along with data visualizations. 

Bringing in the dataset and cleaning the data, which includes handling missing values and fixing inconsistent formatting using tranformations, will be the first steps in getting the data ready for analysis. Following that, we normalized selective features of the dataset to ensure meaningful variability that would better support the analysis. 

In order to acquire a deeper understanding of the data, we visualized it using a variety of visualization techniques, including line charts, histograms, correlation matrix, and heatmaps.

### Fraud Detection Techniques

We employed two main approaches to Fraud Detection.

1. Calculating risk scores for each loan application by comparing its key attributes (Jobs Reported, Loan Amounts, and Loan Amounts per Employee) to other businesses of the same size in the same industry to rank extremely atypical loan applications. We also checked the dataset against specific conditionalities and logic, which we believed if the loan applications are displaying, would make those applications fraudulent.

2. We applied the unsupervised machine-learning algorithm, Isolation Forest anomaly detection, to forecast anomaly scores for loan applications to find the most anomalous loans, which could be signs of PPP loan fraud.

In the cases above, we treated the high-risk and anomaly scores over a threshold as potentially fraudulent.

## Key Findings

1. Of the 1 million loan applications analyzed, more than 9% applications showed at least one indication of potential fraud. 
2. Total 510 billion was approved for loans in the analyzed dataset, out of which 115 billion (22%) is tied to high-risk potentially fraudulent loan applications which is close to the estimated (20%) projected by analysts at state media agencies. 
3. Although California, Texas, and New York had the highest amount of loans processed, Maine, Vermont, and Alabama state had the highest fraud-to-loan ratio.
4. Found misrepresentation in multiple applications that applied through more than one lending agencies disclosing false information such as inconsistent job claims and business information while applying.

Finally, we also conducted exploratory studies on the resulting fraud-identified data to find additional patterns, connections, and trends.

The way this study is designed, we approached it with the intention to aid analysts at SBA and other relevant agencies to help investigate fraud and gain insight into the PPP Loan dataset with the identification of probable PPP loan frauds.

## Python notebook Report
[Detailed Report pynb file](Analysis_Report.pdf)

## Poster
[Fraud Detection Poster](POSTER_PPP_Fraud_Detection.pdf)


