# The Impact of Pandemic Learning Models In Pennsylvania: Assessing  Educational Outcomes Using Matching

## Abstract
The COVID-19 pandemic greatly disrupted education systems, raising questions about the impact of varying school reopening policies. This study examines whether Pennsylvania school districts with similar characteristics but different COVID-19 policies, specifically whether they offered in-person instruction during the 2020-2021 school year, experienced different educational outcomes in the subsequent year. Using district-level data, we matched districts with comparable characteristics that differed in their degree of in-person instruction and analyzed standardized test scores before and after the pandemic. Our findings reveal that districts with more in-person instruction during the studied period experienced significantly smaller declines in math test scores, with an average difference of 0.97 percentage points (t=2.54, df=188) compared to districts without in-person instruction. These results highlight the potential academic benefits of in-person learning amidst unprecedented disruptions.

## Proposal
The proposal has our topic idea, background, intended methodology, potential data sources, and explanation of what success means to us. While working on our project, elements of our proposal shifted. We updated our research question and methodology after thorough research and learning about our initial plan's limitations.

## Data
The data section includes cleaned and raw data files. 

Raw data includes: 
- 2019 pssa school level data.xlsx: Test scores for Pennsylvania state exam in 2019 at the school level
- 2022 pssa school level data.xlsx: Test scores for Pennsylvania state exam in 2022 at the school level
- DistrictFastFacts_20232024.xlsx: Demographic information for Pennsylvania districts
- DistrictMap.csv: Percent of unconnected students by district
- Pennsylvania_Districts_LearningModelData_Final.csv: Whether Pennsylvania districts were in-person, virtual, or hybrid for 2020-2021 school year


Cleaned data includes:
- PA_district_learning_models_clean.csv: Whether Pennsylvania districts were in person, aggregated number of months spent in-person
- district_data.csv: Cleaned demographic covariates
- district_test_data.csv: Average percentage of students in each district who scored proficient in English and Math for both 2019 (pre-COVID) and 2022 (post-COVID) datasets
- matched_data_fromR.csv: Data created from spatial matching in R
- merged_data.csv: Merges learning models, demographic variables, and test data to be used for matching
- descriptive_stats.csv: Table of descriptive stats for merged_data.csv
- stats_by_group.csv: Descriptive statistics for treatment and control group

## Code

Data Cleaning: 
- PA_District_Learning_Model_Code.ipynb: Cleans raw Pennsylvania District Learning Models data to be aggregated by months spend in-person
  - Input: Pennsylvania_District_LearningModelData_Final.csv
  - Output: PA_district_learning_models_clean.csv
- pssa_cleaning.ipynb: Merges 2019 and 2022 pssa school level raw data, groups by distircts, and calulcates the average percentage of students who score proficient in English and Math for both years
  - Input: 2019 pssa school level data.xlsx and 2022 pssa school level data.xlsx
  - Output: district_test_data.csv
- standardization.ipynb: Merges district characteristic data with internet access data, scales numerical features.
  - Input: DistrictFastFacts_20232024.xlsx and DistrictMap.csv
  - Output: district_data.csv
- Merging_Data.ipynb: Combines all datasets to be used for matching analysis
  - Input: PA_district_learning_models_clean.csv, district_test_data.csv, district_data.csv
  - Output: merged_data.csv

Analysis: 
- descriptive_stats.ipynb: creates table of descriptive stats across whole dataset
  - Input: merged_data.csv
  - Output: descriptive_stats.csv
- spatial_matching.ipynb: performs matching and difference of means test using KNN method in Python.
  - Input: merged_data.csv
  - Output: Not used in analysis as it did not result in one-to-one matching
- matching.Rmd: uses MatchIt library to create matched pairs dataset
  - Input: merged_data.csv
  - Output:
    - matching_smd_plot.png
    - matched_data_fromR.csv
- spatial_matching_v2.ipynb: performs difference of means test using matching data exported from R.
  - Input: matched_data_fromR.csv
  - Output:
    - conf_intervals.png
    - matched_pairs_map.html
    - riverview_oldforge.png
    - jeannette_oswayo_highlighted.png
    - penncrest_bristol_highlighted.png
    - matched_pairs_highlighted_map_large.html
- regression.Rmd: OLS model
  - Input: merged_data.csv
  - Output: regression output in Appendix of final paper
 

## Presentation
Our presentation is a brief overview of our project presented in class on 12/10/24. We include information about our motivation, data collection, methods, results, lessons learned, and next steps.

## Report
Our paper cohesively synthesizes the information presented in our repository for easy dissemination and understanding.

## Figures
- conf_intervals.png
- jeanette_oswayo.png
- jeannette_bigbeaver.png
- jeannette_bigbeaver_highlighted.png
- jeannette_oswayo_highlighted.png
- matched_pairs_highlighted_map.html
- matched_pairs_highlighted_map_large.html
- matched_pairs_map.html
- matched_pairs_map.png
- penncrest_baldeagle.png
- penncrest_baldeagle_highlighted.png
- penncrest_bristol_highlighted.png
- penncrest_bristol_map.png
- results.png
- riverview_oldforge.png
- riverview_oldforge_map.png

## Authors
Mena Tetali, Sara Murley, Samantha Rudravajhala 

_McCourt School of Public Policy, Georgetown University_
