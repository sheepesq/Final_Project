# Miscreants Final Project #

<img src = "https://github.com/sheepesq/Final_Project/blob/sheepesq_branch/pictures/citibike_img.png" width = "1100" height = "250">



## Presentation ##
- Our source data is the May data from 2016 to 2019 from [Citi Bike](https://s3.amazonaws.com/tripdata/index.html) to track the changes of rider usage.
- We have selected this topic to determine if machine learning can be used to accurately predict rider destination and/or if they are a citibike Subscriber or a Customer (single user), using the above Citi Bike data. 
- A presentation of our groups data exploration and analysis can be found on our group's [Google Slide](https://docs.google.com/presentation/d/1G3FLyjWYwFp6X2XTLSqYK6MztNdIhv8ljfRgmgMvR7E/edit?usp=sharing). 

## Team Member's Role (Individual Branches) ##
- Square:[Brian](https://github.com/sheepesq/Final_Project/tree/sheepesq_branch)
- Triangle:[John](https://github.com/sheepesq/Final_Project/tree/JohnRamonetti_branch)  
- Circle: [Jen](https://github.com/sheepesq/Final_Project/tree/azarowj_branch)
- X: [Chris](https://github.com/sheepesq/Final_Project/tree/cgruns4_branch)

## Outline ## 

###  Data  ### 
After narrowing the data we will use from the source data, we will then import the data in pgAdmin:

<img src = "https://raw.githubusercontent.com/sheepesq/Final_Project/sheepesq_branch/pictures/pg_admin.png" width = "125" height = "260">

This data can be further explored in our database repository [HERE](https://github.com/sheepesq/Final_Project/tree/azarowj_branch/Database) 

In pgAdmin the as the data is in mutliple tables, it will be merged and connect in a manner that we can then proceede to clean the data. We can clean our data by removing data that is not relevant to our project goal and/or data that contain erroneous information. Once the data has been cleaned, it will be imported into random forest. 

### Analysis Phase ###
To interpret our data we have selected random forest. The reasoning behind selecting Random Forest is explained in the Code section of this Readme file. 

A futher breakdown of our outline can be found [HERE](https://docs.google.com/presentation/d/1R1OLPFjdf9XXZaw83_yAC0UdfwkrlQ2RYni-C662-nk/edit#slide=id.p). On our Google slide presentation.

## CODE ##
### Preliminary data preprocessing and feature engineering: ###
  - The "allmay_df" and "allstations_df" data was imported to pandas dataframes, then preprocessed as follows: Datatypes were determined for all columns. A sample of those two dataframes can be seen below. Null values were checked and null rows were then removed.  All Station Name columns were removed (we have station ID columns in place already).  The "usertype" column was transformed from 'Subscriber'/'Customer' to a binary integer column of  0 / 1.  Starttime and stoptime columns were transformed from string to datetime.  We then split the Starttime column into 'year', 'month', 'day', 'hour' and 'minute'.  For the allStation data, the 'date' column was split into 'year', 'month' and 'day' columns.  A dataframe was created for the Station422 analysis from the allmay_df that was filtered for entries with start station id of 422 (corresponding to the 'W 59 St & 10 Ave' station).  In addition to the above preprocessing/engineering, from this dataset all columns with only 1 (one) unique value were dropped.


allstations_df             |  allmay_df
:-------------------------:|:-------------------------:
![](https://github.com/sheepesq/Final_Project/blob/sheepesq_branch/pictures/allstations_df.png)   |  ![](https://github.com/sheepesq/Final_Project/blob/sheepesq_branch/pictures/Allmay_DF.png)

  
### Description of feature selection: ###
  - The preliminary targets we have used are usertype and gender.  We want to use our models to determine whether we can predict either of these traits based on Citibike useage patterns.  After exploring the data more, we have decided to also determine whether we can predict 'end station' based on data from specific start stations.  We felt that this information would be a useful step toward understanding useage patterns and bicycle migration throughout the Citibike system.  For this we used a subset of the data limited to one busy station (W 59 St & 10 Ave) and used 'end station id' for the target feature.

### Description of how data was split into training and testing sets: ###
  - We are using the default training/testing split of 75/25.

### Explanation of model choice, including limitations and benefits: ###
  - We are initilally using logistic regression and Random Forest (Classifier).  We are analyzing data that is largely categorical and want to try both a simpler evaluation and a more robust evaluation.  Random forest is appropriate because it can handle binary features, categorical features, and numerical features, with little pre-processing that needs to be done.  We expect to investigate other neural network approaches as well, so the data will be scaled and prepared for those models too.  Because our datasets are relatively large, we will use a simpler logistic regression model as well.

### Explanation of changes in model choice and training of the model
  - For the first question of whether the data can predict usertype, we have used the Random Forest model, Logistic Regression and a basic Neural Network.  For the new question of whether the data can predict End Station based on Start Station data, we used Random Forest with success, but Logistic Regression and a basic Neural Network have both given unsatisfactory results.
### Description of current accuracy score
  - Accuracy score for predicting usertype is currently as follows: Random Forest 95.8%; Logistic Regression 90.9%; Neural Network 95.1%.  For predicting end station based on start station data, our current accuracy score is as follows:  Random Forest 90.5%.

### The Machine learning code comprises 6 .ipynb files:
  - [Citibike_project.ipynb](Citibike_project.ipynb):  
Initial exploratory/project discussion code. No final project code.
  - [Citibike_project-Copy1.ipynb](Citibike_project-Copy1.ipynb):  
Preprocessing and exploratory code for May datasets and Station datasets, culminating in allmay_cleaned.csv and allstations_cleaned.csv.
  - [Citibike_RF.ipynb](Citibike_RF.ipynb):  
Analysis (Random Forest, Logistic regression, neural network)
  - [Citibike_allMay_additional_analysis.ipynb](Citibike_allMay_additional_analysis.ipynb):  
Google Collab nb for additional processing, feature engineering and analysis on allMay data
  - [Citibike_allStations_exploration_addl_processing.ipynb](Citibike_allStations_exploration_addl_processing.ipynb):  
Addl. preprocessing, feature engineering and exploratory code for allStations data
  - [Citibike_station422.ipynb](Citibike_station422.ipynb):  
Code for station 422 analysis, to determine predictability of "end stations"


## Tableau ##
An interactive display has been created on [Tableau](https://public.tableau.com/app/profile/christopher.grunsfeld/viz/Citibike-FinalProject/NYCCITBIKEDASHBOARDMAIN?publish=yes). It provides the user with easy to interpret data charts that are interactive and a map that allows the user to select one of the many Citi Bike stations to learn more about it. 


