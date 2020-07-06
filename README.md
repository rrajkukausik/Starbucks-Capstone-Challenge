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

This challenge is one of the final projects for Udacity Data Science Nanodegree course. For this project, we have datasets from Starbucks which contain simulated data that mimics customer behaviour on the Starbucks rewards mobile app.

The reason why companies use different offers or discounts campaigns is to stimulate customers to come more often and spend more. This ultimately helps to increase the revenue and profit for the company. In this project I'll try to link the response to the offers with the overall customer behaviour. This can help us to understand the structure of the customer and develop strategies for different groups.

The end goal is to find some segments of the current customers depending on their behaviour and figure out which segment would be the most interesting for a further advertisement campaign and where we can change the frequency of offers.


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

  *  I was managed to find 5 different groups with unsupervised machine learning algorithm (K-Means). With this information, a company can implement some different marketing campaigns for each group depending on the general strategy.

  * For this project, we have data only for the one-month period, but it would be interesting to analyze a longer period, like several months or  even  years. Then we can see the structure (clusters) changes over time and could also estimate the impact of changing offer’s parameters like frequency of campaign, offers’ difficulty, duration and reward.

   
   For more information you can refer to my blog post. 
   **The Medium Link For The Project Is  https://medium.com**. 

## Acknowledge
  Besides, you must know that the project is under the Udacity Data Science Capstone Project, and the dataset is provied by the Starbucks.

## Author
* **Raj Kumar Kausik**
* **Email-** - rrajkukausik@gmail.com



