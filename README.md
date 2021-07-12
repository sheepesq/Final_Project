# Miscreants Final Project #

## Presentation ##
- Our source data is the May data from 2016 to 2019 from [Citi Bike](https://s3.amazonaws.com/tripdata/index.html) to track the changes of rider usage.
- We have selected this topic to determine if machine learning can be used to accurately predict rider destination and/or if they are a citibike Subscriber or a Customer (single user), using the above Citi Bike data. 

## Team Member's Role (Individual Branches) ##
- Square:[Brian](https://github.com/sheepesq/Final_Project/tree/sheepesq_branch)
- Triangle:[John](https://github.com/sheepesq/Final_Project/tree/JohnRamonetti_branch)  
- Circle: [Jen](https://github.com/sheepesq/Final_Project/tree/azarowj_branch)
- X: [Chris](https://github.com/sheepesq/Final_Project/tree/cgruns4_branch)

## Communication protocols ##
-Team has exchanged personal phone numbers, share information over slack and have scheduled meets over zoom

## Outline ## 

###  Data  ### 
After narrowing the data we will use from the source data, we will then import the data in pgAdmin:

<img src = "https://raw.githubusercontent.com/sheepesq/Final_Project/sheepesq_branch/pictures/pg_admin.png" width = "125" height = "260">

In pgAdmin the as the data is in mutliple tables, it will be merged and connect in a manner that we can then proceede to clean the data. We can clean our data by removing data that is not relevant to our project goal and/or data that contain erroneous information. Once the data has been cleaned, it will be imported into random forest. 

### Analysis Phase ###
To interpret our data we have selected random forest this is because it will works well with both categorical and numerical data. An advantage to random forest is that scaling or transformation of variables is usually not necessary. In addition, Random Forest algorithm is very stable, if we expand the data of the overall algorithm, it will not be affected much since the new data may impact one tree, but it is very unlikley that it will impact all the trees. The main con to random forest is that the user does not have a tremendous control over what the model does and the best one can do is provide different parameters.
With the results of our analysis 


## Google Slides ##

LINK HERE

## CODE ##
#### Preliminary data preprocessing and preliminary feature engineering:
  - The "allmay_df" and "allstations_df" data was imported to pandas dataframes, then preprocessed as follows: Datatypes were determined for all columns.  Null values were checked and null rows were then removed.  All Station Name columns were removed (we have station ID columns in place already).  The "usertype" column was transformed from 'Subscriber'/'Customer' to a binary integer column of  0 / 1.  Startime and stoptime columns were transformed from string to datetime.
  
#### Description of preliminary feature selection:
  - The preliminary targets will be usertype and gender.  We want to use our models to determine whether we can predict either of these traits based on Citibike useage patterns.

#### Description of how data was split into training and testing sets:
  - We are using the default training/testing split of 75/25.

#### Explanation of model choice, including limitations and benefits:
  - We are initilally using logistic regression and Random Forest (Regressor).  We are analyzing data that is largely categorical and want to try both a simpler evaluation and a more robust evaluation.  Random forest is appropriate because it can handle binary features, categorical features, and numerical features, with little pre-processing that needs to be done.  We expect to investigate other neural network approaches as well, so the data will be scaled and prepared for those models too.  Because our datasets are relatively large, we will use a simpler logistic regression model as well.




