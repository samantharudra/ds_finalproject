# The Impact of Pandemic Learning Models In Pennsylvania: Assessing  Educational Outcomes Using Matching

## Description
As the education system grapples with the side effects of the Covid-19 Pandemic, we question if similar school districts with different covid-19 policy choices have had different educational outcomes in the year following. We first analyzed district level data in the Commonwealth of Pennsylvania, looking at how long districts were in-person during the 2020-2021 school year. Using spatial matching to create pairs of similar districts based on demographics but with different Covid policies, we then examined their test scores from before and after the pandemic.

## Proposal
The proposal has our topic idea, background, intended methodology, potential data sources, and explanation of what success means to us. While working on our project, elements of our proposal shifted. We updated our research question and methodology after thorough research and learning about our initial plan's limitations.

## Data
The data section includes cleaned and raw data files. 

Raw data includes: 
- 2019 pssa school level data.xlsx: Test scores for Pennsylvania state exam in 2019 at the school level
- 2022 pssa school level data.xlsx: Test scores for Pennsylvania state exam in 2022 at the school level
- DistrictFastFacts_20232024.xlsx: Demographic information for Pennsylvania districts
- DistrictMap.csv: Percent of unconnected students by district
- Pennsylvania_Districts_LearningModelData_Final.csv: Whether Pennsylvania districts were in person, virtual, or hybrid for 2020-2021 school year
- SchoolFastFacts_20232024.xlsx: Demographic information for Pennsylvania schools

Cleaned data includes:
- PA_district_learning_models_clean.csv: Whether Pennsylvania districts were in person, aggregated number of months spent in-person
- district_data.csv: Cleaned demographic covariates
- district_test_data.csv: Average percentage of students in each district who scored proficient in English and Math for both 2019 (pre-COVID) and 2022 (post-COVID) datasets
- matched_data_fromR.csv: Data created from spatial matching in R
- merged_data.csv: Merges learning models, demographic variables, and test data to be used for matching
- stats_by_group.csv: Descriptive statistics for treatment and control group

## Code

Data Cleaning: 
- PA_District_Learning_Model_Code.ipynb: 
- pssa_cleaning.ipynb: 
- standardization.ipynb: merges district characteristic data with internet access data, scales numerical features. 
- merging_data: combines all datasets

Analysis: 
- descriptive stats: creates table of descriptive stats across whole dataset
- clustering.ipynb: performs clustering analysis on the final dataset (not  included in final analysis)
- spatial_matching.ipynb: performs matching and difference of means test using KNN method in Python. 
- spatial_matching_v2.ipynb: performs difference of means test using matching data exported from R. 
- regression.Rmd: OLS model 
- matching.Rmd: uses MatchIt library to create matched pairs dataset 


## Presentation
Our presentation is a brief overview of our project presented in class on 12/10/24. We include information about our motivation, data collection, methods, results, lessons learned, and next steps.

## Paper
Our paper cohesively synthesizes the information presented in our repository for easy dissemination and understanding.

## Figures

## Authors
Mena Tetali, Sara Murley, Samantha Rudravajhala 

_McCourt School of Public Policy, Georgetown University_
