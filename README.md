# Miscreants Final Project #

## Presentation ##
- Our source data is the May data from 2016 to 2019 from [Citi Bike](https://s3.amazonaws.com/tripdata/index.html) to track the changes of rider usage.
- We have selected this topic to determine if machine learning can be used to accurately predict rider destination and/or if they are a citibike Subscriber or a Customer (single user), using the above Citi Bike data. 

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
### Preliminary data preprocessing and preliminary feature engineering: ###
  - The "allmay_df" and "allstations_df" data was imported to pandas dataframes, then preprocessed as follows: Datatypes were determined for all columns. A sample of those two dataframes can be seen below. Null values were checked and null rows were then removed.  All Station Name columns were removed (we have station ID columns in place already).  The "usertype" column was transformed from 'Subscriber'/'Customer' to a binary integer column of  0 / 1.  Startime and stoptime columns were transformed from string to datetime.


allstations_df             |  allmay_df
:-------------------------:|:-------------------------:
![](https://github.com/sheepesq/Final_Project/blob/sheepesq_branch/pictures/allstations_df.png)   |  ![](https://github.com/sheepesq/Final_Project/blob/sheepesq_branch/pictures/Allmay_DF.png)

  
### Description of preliminary feature selection: ###
  - The preliminary targets will be usertype and gender.  We want to use our models to determine whether we can predict either of these traits based on Citibike useage patterns.

### Description of how data was split into training and testing sets: ###
  - We are using the default training/testing split of 75/25.

### Explanation of model choice, including limitations and benefits: ###
  - We are initilally using logistic regression and Random Forest (Regressor).  We are analyzing data that is largely categorical and want to try both a simpler evaluation and a more robust evaluation.  Random forest is appropriate because it can handle binary features, categorical features, and numerical features, with little pre-processing that needs to be done.  We expect to investigate other neural network approaches as well, so the data will be scaled and prepared for those models too.  Because our datasets are relatively large, we will use a simpler logistic regression model as well.

Our code for the above can be found [HERE](https://github.com/sheepesq/Final_Project/blob/JohnRamonetti_branch/Citibike_project-Copy1.ipynb). 



