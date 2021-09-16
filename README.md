# UdacityStarbucksCapstone
Starbucks Capstone Project for Data Scientist and Machine Learning Engineer Nanodegrees

## Table of Contents
1. [Introduction](#intro)
2. [Prerequisites](#prereq)
3. [Repository Structure](#repo)
4. [Results Summary](#results)
5. [Medium Article](#med)
6. [License](#lic)
7. [Acknowledgments](#ack)

<a name="intro"></a>
## Introduction
Three datasets are provided by Starbucks. The first is a list of 10 promotions that were sent to customers, the second is a list of 17,000 customers with limited demographics information and the third is a transcript which details when each customer received, viewed and completed and offer and when they completed a transaction. 

The purpose of these promotions are to bring existing customers to the store more often as well as to introduce new customers, who may benefit from a BOGO (buy one get one free) offer with an existing customer. Therefore there is a cost associated to offering these promotions to customers in the form of discounted or free products, with the aim to bring in existing customers more often and to bring in new customers to the stores, then ideally generate more profit in the long-term.

In this dataset there are different types of customer. Some are loyal customers who are not affected by the promotions, others already spend a lot of money in stores and the promotions are likely to not have any impact on their spend. The customers we are interested in are the ones who view and then complete the offers. So the question that we would like to answer from this dataset is: 
Can we identify, through customer demographics, which customers are likely to intentionally complete an offer? 
If this question can be answered, we can create a model to identify which customers are more likely to complete offers and then target those types of customers in future to maximise profit potential. 

<a name="prereq"></a>
## Prerequisites
The Jupyter Notebook provided in this repository uses the following:
- Python 3.6
- numpy
- pandas
- matplotlib
- scikit-learn
- math
- json

<a name="repo"></a>
## Repository Structure
The repository is structured as follows:
- data folder 
  - portfolio.json - list of promotions
  - profile.json - list of customers and their demogrpahics
  - transcript.json - list of customer transactions and interactions with offers
- Starbucks_Capstone_notebook.ipynb - the notebook containing data cleaning, pre-processing and modelling  
- modelling_data.csv - the modelling data (cleaned and pre-processed)
- pic1.png - image for the notebook
- pic2.png - image for the notebook
- README.md - this file

<a name="results"></a>
## Results Summary
Four types of classifier model were created:
1. Logistic Regression (LR)
2. K-Nearaest-Neighbours (KNN)
3. Support Vector Classifier (SVC)
4. Random Forest ensemble (RF) 

The inputs to the models were the age and income of each customer, and the classifier would determine if a customer would complete a BOGO or discount promotion offer. The benchmark set out in the project was to have a classification F1 score of 65% or better. The F1 score is used due to imbalanced classes for BOGO and Discount offer completion, so classification accuracy would not be a suitable metric. A 65% score would provide some confidence to making business decisions based on the model, because the default position is to guess which would be a 50% chance of correct classification. 

In all cases, the models did not pass the 65% benchmark criteria. The LR and SVC model has the highest overall F1 scores but looking at the data, the classification does not seem to have captured any underlying structure in the data, they seem to attempt some separation between customers who did or did not complete an offer based more on salary. On the other hand, the KNN and RF models appeared to have a greater spread of predictions across the whole input domain and appear to have captured some structure from the data, but both had F1 scores just slightly better than 50% which fell far short of the desired predictability. Therefore, the answer to the question "Can we identify, through customer demographics, which customers are likely to intentionally complete an offer?" is no, with the current dataset and model structure.

Solving this type of problem based on the available data is very challenging because the preprocessed data visualisations appear to show that there may not be a discernible pattern related to offer completion based on age and income alone. There are also datapoints in the dataset that have overlapping classes, so for the same age and income one person does complete an offer and another doesn't. These types of data will make the classification more difficult. One way to remedy this is to attempt some further form of separation in the input data by adding new features and dimensions, such as gender, ethnicity, etc. These new dimensions would serve to spread the data out more spatially, and the addition of these new dimensions may unveil structural patterns in the data that can be seen and captured by the model that the current structure with 2 inputs cannot capture. 

<a name="med"></a>
## Medium Article
An article has been published on Medium which is the full report that covers the data exploration through to modelling and conclusions. The article can be found [here](https://medium.com/@r.parekh90/data-scientist-nanodegree-capstone-project-starbucks-promotions-cb54a6690802).

<a name="lic"></a>
## License
This project is created using some content (data and code) provided by Udacity and Starbucks under the Data Scientist Nanodegree. The code is customised by the author of this repository. The author declares that the customised code is free to use and waives all copyright or related rights to this work.

<a name="ack"></a>
## Acknowledgements
* [Udacity Data Scientist Nanodegree](https://www.udacity.com/course/data-scientist-nanodegree--nd025)
* Starbucks
