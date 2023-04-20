# SC1015_Z137_Grp6
For the Mini-Project in SC1015 (Introduction to Data Science and Artificial Intelligence), we performed analysis on the structural data of buildings from the 2015 Gorkha earthquake in Nepal. (http://eq2015.klldev.org/#/download)

## Problem Definition
- What structural features of a building contribute to the building's damage grade?
- Which building materials, that are not earthquake proof, can better withstand an earthquake?
Our group's perspective is that earthquakes are costly and disastrous depending on the preparations made beforehand. If we do not prepare, it is highly unlikely that we might come out of the disaster unscathed. Through this project, we want to understand the amount of damage caused by the earthquake based on the building material and building structure. We hope to be able to apply the findings of our project to help us predict the amount of damages caused by earthquakes depending on the condition of the building structure in the future. 

## Members
-	Caren Tan Xin Yao
-	Joelle Chew Ningxi
-	Lee Bohui

## Files Included
1.	csv_building_structure.csv -->dataset
2.	SC1015 Mini Project.ipynb
      - Data Cleaning and Preparation
      - Exploratory Data Analysis
      - Preparation for Machine Learning
      - Machine Learning: Logistic Regression (building materials), Linear Regression (building age), Decision Tree

## Notebook Details
### Data Cleaning and Preparation
-	We first removed the columns ‘building_id’, 'district_id', 'vdcmun_id', 'ward_id', 'count_floors_pre_eq', 'count_floors_post_eq', 'plinth_area_sq_ft', 'height_ft_pre_eq', 'height_ft_post_eq’ as we felt that they did not have any relation to the building structure and building material which are our main focus.
-	We visualised our numeric variable, age_building (ie. age of building) using a boxplot and found that the age ranges from 0 to 200 before jumping straight to 999. 
    - This jump was very unusual and hence, we decided to remove the rows with 999 for age_building from the dataset.
- There were some blank data in the columns ‘damage_grade’, ‘technical_solution_proposed’, ‘position’ and ‘plan_configuration’.
  -	We found the mode of these variables and replace the blanks with them
### Exploratory Data Analysis
-	We plotted the bar graphs of ‘damage_grade’, ‘ foundation_type’, ‘ground_floor_type’, ‘other_floor_type’, ‘roof_type’ and ‘land_surface_condition’ to see the distribution of the data over the categorical classification of each variable.
-	Created two data frames, damage_to_type and damage_to_superstructure, for future comparison between
    -	 'foundation_type', 'ground_floor_type', 'other_floor_type', 'roof_type', 'land_surface_condition' 
    -	'has_superstructure_adobe_mud', 'has_superstructure_other', 'has_superstructure_rc_engineered', 'has_superstructure_rc_non_engineered', 'has_superstructure_bamboo', 'has_superstructure_timber', 'has_superstructure_cement_mortar_brick', 'has_superstructure_mud_mortar_brick', 'has_superstructure_mud_mortar_stone', 'has_superstructure_stone_flag', 'has_superstructure_cement_mortar_stone' 

    and 'damage_grade' respectively.
### Preparation for Machine Learning
- We found the strength of the relationship the building materials, ‘age_building’ (predictor) and ‘damage_grade’ (response) using correlation and heatmaps.
- From the heatmap, we decided to choose the variables with higher correlation to ‘damage_grade’ (ie. correlation that have 2 d.p.) to use in our Machine Learning Models.
    - Variables we are using: ‘foundation_type’, ‘ground_floor_type’, ‘ other_floor_type’, ‘roof_type’, ‘has_superstructure_rc_engineered’, ‘has_superstructure_rc onon engineered’, ‘has_superstructure_bamboo’, ‘has_superstructure_timber’, ‘has_superstructure_cement_mortar_brick’, ‘has_superstructure_mud_mortar_stone’ and ‘age_building’
### Machine Learning
-	We use one-hot encoding for all the variables mentioned prior to improve the prediction and performance of our machine learning model – logistic regression – since our categorical variables does not have any ranking for its categorical values.
-	We have also chosen to use decision tree because 

## References:
