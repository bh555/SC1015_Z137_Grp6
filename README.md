# SC1015 (Introduction to Data Science and Artificial Intelligence)
# Lab Grp Z137, Team 6
# Project Title: Analysis of 2015 Gorkha Earthquake in Nepal

## Members
-	Caren Tan Xin Yao
-	Joelle Chew Ningxi
-	Lee Bohui

## Project Folder Includes
1.	csv_building_structure.zip (Data set from [klldev.org](http://eq2015.klldev.org/#/download))
2.	SC1015 Mini Project.ipynb

#### Note: The excel sheet is compressed into a zip file due to upload size constraints by Github.

##  Libraries used:
- [Graphviz](https://graphviz.org/download/) (Ensure to install both executable and python package.)
- Pandas
- sklearn
- numpy
- seaborn
- matplotlib
- Dython
- IPython
- scipy

---

## Summary of Project
For our Mini-Project, we performed analysis on the structural data of buildings from the 2015 Gorkha earthquake in Nepal. The Earthquake had a magnitude of 6.5, followed by an aftershock of roughly 5.0 magnitude.

### Introduction
Our group's perspective is that earthquake's are costly and disastrous depending on the preparations made beforehand. If we do not prepare, it is highly unlikely that we might come out of the disaster unscathed. Through this project, we hope to be able to apply the findings of our project to help us predict the amount of damage caused by earthquakes depending on the condition and make of buildings in the future. Subsequently, we would also like to understand whether the age of a building can contribute to the building's damage since it takes corrosion and deterioration into account.

#### So we came up with 2 objectives for our project:
1. Which building materials contribute to a building's damage grade?
2. Does building age contribute to a building's damage grade?

### Step 1: Data Preprocessing/Preparation
We removed outlier buildings that featured the age of 999 since they were too distant from the other buildings and might create funny results in the later steps. At the same time, we conducted basic data cleaning procedures on the data set. For example, blanked cells for Damage Grade were fited with the highest damage grade which is "Grade 5". You may take a look at our notebook for how we visualized our dataset and investigated its statistics.

### Step 2: Exploratory Data Analysis (EDA)
Our dataset provided a wide range of categorical variables for us to use, but we narrowed it down to a select few by using an data analysis tool called "Associations" to help us see the variables correlation strength with damage grade. Upon doing so, we picked out the relevant variables and grouped them according to their features. The names of the two groups are "Building Foundation" Set and "Superstructure Material" Set. You may refer to the notebook for more information and to see the visualizations.

### Step 3: Machine Learning
Our group has chosen to use Chi-Square Value, Logistic Regression and Random Forest to analyse and seek answers to our problem statements. Before proceeding, we used Chi-Square Value to find out the importance of each variable. We did this so as to get a feel of which variables to focus our attention on during Logistic Regression and Random Forest phase. We chose to use Logistic Regression to see the prediction accuracy and reliability of each variable that we picked and if there was a need to reinforce it by using another Machine Learning Model. Our findings showed that each variable had a weak prediction accuracy of around 0.4. Hence, we chose to use Random Forest Model since its algorithm compensates the weak predictions of multiple variables and decision trees. We decided not to use Decision Tree Model since it uses a single decision making process and does not best fit our wide range of variables that need to be considered. Please refer to the notebook for the details of our experimentation steps.

### Step 4: Conclusion
For this step, we used the results of Chi-Square method and Logistic Regression Model against our concluding results from the Random Forest Tree to find our answers. Our answer to the first problem statement, we found that the superstructure materials: Reinforced Concrete (RC) Non-engineered and Cement-Mortar Brick; are the most significant contributors to a building damage grade. In addition, they are joined by the foundation materials RC Engineered and Bamboo or Timber.

For our second problem statement, building age **may** be a contributor to a building's damage grade. Random Forest showed that building age was a popular choice when chosen together with the "Superstructure Material" Set and on the other hand, it was not a popular choice when chosen together with the "Building Foundation" Set. Although, a caveat to keep in mind is that the accuracy of the Random Forest were around 0.4.

To conclude, after going through the EDA and Machine Learning step. We believe that our data set has multiple categorical data to use, but does not have enough numerical data to help us get a better prediction of the damage grade. In reality, a building of any shape or size is prone to collapse or damage. Parameters such as number of floors and square feet area of the building's base are not good descriptors of a building and hence cannot be used as suitable predictors for damage grade.

---

## What we have learnt:
- One-Hot Encoding
    - One-Hot Encoding is a method to help convert categorical data, which are labels, into a binary variable. Despite some Machine Learning models being able to accept categorical data directly, it is difficult to use categorical data with other Machine Learning Models since there are hard limits to what we can do in the machine learning step. Hence, converting categorical data to a numerical data of binary classification is necessary.

- Chi-Square Value
    - Chi Square is a feature selection technique used for categorical data to display the importance of each variable in order of how it influences the response. It checks if the variables have a strong relationship with each other. The chi value tells you the importance of each variable with respect to the other variables. The higher the chi value, the more important the variable is.

- Associations (Dython Library)
    - It is a data analysis tool which is able to take in categorical data in order to generate a heatmap. Useful for finding the correlation of categorical data, numerical data can be used with this tool as well. You can see this in our notebook under "Preparation for Machine Learning" before Machine Learning step.

- Logistic Regression Model
    - Logistic Regression has the ability to take categorical data as inputs and come up with a regression model to predict categorical values using the categorical data received. In our project, we use one-hot encoded data, which are converted into binary classification data, and used them as predictors to predict damage grade in order to find which material contributes to damage grade.

- Random Forest Model
    - Random Forest Model is a classification algorithm that creates many decision trees and combines them into a single tree. It is done so as to compensate for the loss in prediction accuracy and reliability of each decision tree. For our project, through our logistic regression we found that we had weak predictions. Hence, we decided to use Random Forest to aid us in getting a better accurate and reliable prediction. Unfortunately, we did not get a better prediction and we believe that it has to do with not having enough numerical variables which can be used with our prediction.

- Graphviz
    - Useful to visualize models that do not have display support in their libraries. E.g. Sklearn Random Forest.

---

## References:
- https://datatofish.com/random-rows-pandas-dataframe/
- https://stackoverflow.com/questions/65147132/how-to-set-the-hue-order-in-seaborn-plots
- https://www.datacamp.com/tutorial/random-forests-classifier-python
- https://www.statology.org/plot-logistic-regression-in-python/
- https://www.youtube.com/watch?v=v6VJ2RO66Ag
- https://www.youtube.com/watch?v=InZ0n2knz1E
- https://www.youtube.com/watch?v=6N9H9KxdZdk&t=37s
- https://www.youtube.com/watch?v=sYZ2KfT7Ryc 
- https://neptune.ai/blog/performance-metrics-in-machine-learning-complete-guide
- https://www.ibm.com/topics/underfitting
- https://www.analyticsvidhya.com/blog/2021/09/gradient-boosting-algorithm-a-complete-guide-for-beginners/
- https://graphviz.readthedocs.io/en/stable/manual.html
- http://eq2015.klldev.org/#/download
