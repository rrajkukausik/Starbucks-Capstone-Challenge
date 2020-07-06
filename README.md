# UDACITY FINAL CAPSTONE PROJECT

## STARBUCKS CAPSTONE CHALLENGE

**Table Of Contents**

```
1. Installation
2. Project Motivation
3. Project Overview
4. File Structure
5. File Descripton
6. Results
7. Acknowledgement
```


## Installation

The project is supported by Python 3.x (Hint: directly install the Anaconda distribution), libraries and packages:


```
  1. Numpy
  2. Pandas
  3. Seaborn
  4. Matplotlib
  5. Scikit-learn
  6. json
  7. warnings
  8. imp
  8. Ipython
```


## Project Motivation

This project aims at discovering customer behavior based on simulated Starbucks app data. 
Datasets that contains offer information, customer demography, records of transactions, and customer-offer interaction data.


## Project Overview

The data set contains three files, which are simulated on the Starbucks rewards mobile app, which focuses on the customers' transactions behavior. Our topic targets are that how the effect of the reward offer is and is there a relationship between the reward offer and the users' demographic information. From the company side, it is interesting that whether the customers are more willing to pay more money in the Starbucks after the promotion.

When we analyze the users' willing, we use the amount as the target label and the users' demographic information and the promotion type as explanatory variables. Of course, the target label is continuous value, we consider that the Supervised learning is a right way to build model.

## File Structure

```
├── README.md
├── Starbucks_Capstone_notebook.ipynb
├── data
   ├── portfolio.json
   ├── profile.json
   └── transcript.json
```

## File Description

* Starbucks_Capstone_notebook.ipynb

  The notebook is used to run code, which contains data wrangling, data exploration, and model build


* README.md

  The final report file

* Data Sets
  
  The data is contained in three files:

  **portfolio.json** - containing offer ids and meta data about each offer (duration, type, etc.)
  **profile.json** - demographic data for each customer
  **transcript.json** - records for transactions, offers received, offers viewed, and offers completed
  
  Here is the schema and explanation of each variable in the files:

  **- portfolio.json -**

  id (string) - offer id
  offer_type (string) - type of offer ie BOGO, discount, informational
  difficulty (int) - minimum required spend to complete an offer
  reward (int) - reward given for completing an offer
  duration (int) - time for offer to be open, in days
  channels (list of strings)

  **- profile.json -**

  age (int) - age of the customer
  became_member_on (int) - date when customer created an app account
  gender (str) - gender of the customer (note some entries contain 'O' for other rather than M or F)
  id (str) - customer id
  income (float) - customer's income
  
  **- transcript.json _**

  event (str) - record description (ie transaction, offer received, offer viewed, etc.)
  person (str) - customer id
  time (int) - time in hours since start of test. The data begins at time t=0
  value - (dict of strings) - either an offer id or transaction amount depending on the record




## Results

1. **Effect Of Different Promotion**
   The total number of the users is **17,000**. But after the promotion done, there are **4,332** members actively going to the Starbucks. The ratio is **25.48%**.

   - The amount of promotion strategy is almost the same.
     1. The largest one is the discount has **10,101**
     2. The smallest one is the **BOGO** has **8,568**
     3. The informational is the middle one, has **9,548**
   - But there is a significant  growth rate
     1. In totally, there is a positive effect at each strategy
     2. The **informational** make a high improve to attract the customers

2. **Relationship Between Demographic Information And Promotion Type**
   Take a deep into the users demographic information with the different promotion strategy.   

   - Firstly, the gender other doesn't have apparent significance
   - The new users who don't have detailed demographic value can attract by the informational promotion
   - The young low-income male users and the old low-income male can attract by the informational promotion. At the same time, the rest promotion types do have a significant impact. In totally, the young members are much more active than the other age users, at the low-income level
   - Above the medium-high income level, the discount promotion type makes a much more improve the buying amount
     In a word, the informational promotion type affects the new member users; the discount promotion type affects the high-income member users; the pop users are the young medium-income, which exclude the non-demographic information member.

3. **Model Result**

   We build three models: the linear regression is a basic model, then the model is optimized by the decision tree regression and the random forest regression. At the same time, we use the GridSearchCV to tune the model. The last two model can analyze the important feature.

   * The last two model get a better score than the basic model. The mean squared value is closed to **1**, and the R square value is **0.5925** about the test data

   * According to the feature importance, the feature high-income level, the feature became-member date, and the female gender are important demographic information. At the promotion side, the promotion duration is more important than the promotion type; the BOGO type and the discount type are not important.

   
   For more information you can refer to my blog post. 
   **The Medium Link For The Project Is  https://medium.com**. 

## Acknowledge
  Besides, you must know that the project is under the Udacity Data Science Capstone Project, and the dataset is provied by the Starbucks.

## Author
* **Raj Kumar Kausik**
* **Email-** - rrajkukausik@gmail.com



