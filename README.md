## Project Overview

This project involved surveying and analyzing markets across selected African countries to understand consumer perceptions, economic sentiment, employment conditions, financial behavior, and banking preferences.

The survey data was cleaned, standardized, validated, and analyzed using Python and Excel. The analysis examined demographic characteristics, economic expectations, employment perceptions, banking behavior, customer satisfaction, and factors influencing consumers' relationships with financial institutions.

The project ultimately aimed to identify market-level trends and differences between countries and demographic groups, translating survey responses into actionable insights that can support market research, business strategy, and data-driven decision-making.on and version control
## Project Objectives

Survey selected African markets to understand consumer and market conditions.
Analyze consumer perceptions of economic conditions and future expectations.
Assess perceptions of employment opportunities and job-market conditions.
Examine consumer banking behavior and relationships with financial institutions.
Identify key factors influencing bank choice, customer satisfaction, and customer retention.
Compare market trends and consumer sentiment across countries and demographic groups.
Clean, standardize, validate, and transform survey data for reliable analysis.
Generate actionable market insights to support data-driven business and market decisions.

## Dataset

The dataset contains 3,263 survey responses collected across selected African markets, covering demographic, socioeconomic, economic, employment, and financial behavior indicators.

The survey included 38 initial variables, with questions covering areas such as:

Country and demographic characteristics
Age and gender
Education and employment status
Perceptions of job opportunities
Expectations about economic conditions
Ability to meet regular expenses
Banking relationships and bank usage
Customer satisfaction
Reasons for choosing and staying with financial institutions

During the data preparation process, 72 duplicate respondent records were identified and removed, resulting in 3,191 unique responses based on email addresses.

The dataset was subsequently cleaned and standardized by removing duplicate fields, consolidating equivalent survey responses, standardizing categorical values, handling missing values, and preparing the data for cross-country and demographic analysis.

## Tools & Technologies
Python — Data cleaning, transformation, standardization, validation, and automation
Pandas — Data manipulation and analysis
NumPy — Numerical analysis and data processing
Microsoft Excel — Data cleaning, mapping, pivot tables, formulas, and exploratory analysis
Power BI — Data visualization, dashboard development, and presentation of market insights
Statistical Analysis — Descriptive statistics, cross-tabulation, percentages, and hypothesis testing

## The cleaning process

Performed the following steps  to prepare the dataset for pivot table summarization and statistical analysis

Data Cleaning Process
The following steps were performed to prepare the dataset for pivot table summarization and statistical analysis.
1. Merged duplicate question columns

Some survey questions were duplicated across multiple columns, with each respondent answering only one of the duplicate columns. These columns were merged into a single column by returning the first non-blank response.
Formula used (example: columns Q, R, S, T, U, V, and W contained responses to the same question):
=IF(Q2<>"",Q2,IF(R2<>"",R2,IF(S2<>"",S2,IF(T2<>"",T2,IF(U2<>"",U2,IF(V2<>"",V2,W2))))))

2. Removed duplicate columns
The original duplicate columns were deleted, leaving a single column for each survey question.

3. Removed duplicate respondent records
Duplicate respondents were identified using Email Address as the unique identifier.
Total responses before deduplication: 3,263 
Unique email addresses: 3,191 
Duplicate responses removed: 72

4. Checked for missing values
Missing values were assessed using the COUNTBLANK() function for each column.
No unexpected missing values were identified. Blank cells found in the banking section resulted from the survey's conditional questions (skip logic), where respondents without bank accounts were not required to answer bank-related questions

5. Removed French duplicate columns
Duplicate French-language columns were removed, leaving a single English version of each survey question.

6. Removed French text  responses
Some response cells contained both English and French . The English portion was extracted to create an English-only dataset.
Formula used:
=TRIM(LEFT(H2,FIND("/",H2)-1))

7. Text trimming and capitalization
Leading and trailing spaces were removed using the TRIM() function, and text capitalization was standardized using the PROPER() function to improve consistency across  responses.
Formula used:
=PROPER(TRIM(A2))

8. Standardized text responses
Semantically equivalent responses (i.e, Nothing, Nil, N/A, No, Nope, etc.) were standardized to "None" using a response mapping table to ensure consistency during analysis.
Formula used:
=IFERROR(XLOOKUP(A2,'Response Mapping'!$A:$A,'Response Mapping'!$B:$B),A2)

9. Final validation
A final quality check was performed to confirm that:
Duplicate respondent records had been removed. 
Duplicate question columns had been consolidated. 
The dataset contained English-only questions and responses. 
No unexpected missing values remained. 
Text responses had been standardized. 
The dataset was ready for pivot table summarization, descriptive statistics, and inferential statistical analysis.
<img width="2480" height="1312" alt="image" src="https://github.com/user-attachments/assets/0b95dfef-ee19-4334-bb29-48c9f28131f7" />
