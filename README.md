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

Then the data will be cleaned by removing columns that are not relevant to our project goal and columns that contain erroneous information. Once the data has been cleaned the tables will be joined and where possible data tables will be merged. Following that step, the data will be imported into random forest where we will tnterpret the output. 

### Analysis Phase ###
To interpret our data we have selected random forest this is because it will works well with both categorical and numerical data. An advantage to random forest is that scaling or transformation of variables is usually not necessary. In addition, Random Forest algorithm is very stable, if we expand the data of the overall algorithm, it will not be affected much since the new data may impact one tree, but it is very unlikley that it will impact all the trees. The main con to random forest is that the user does not have a tremendous control over what the model does and the best one can do is provide different parameters.



## Google Slides ##

LINK HERE

## CODE ##

LINK HERE

