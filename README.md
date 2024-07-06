  # Improve City 311 Services Using ML/AI: A Pilot Project of Predicting Overdue 311 Calls

![image](https://github.com/Sandysmile/Capstone/assets/20648423/ba6e4052-9a03-451b-bfd9-a3af9d4747cd)


## Capstone ML Project Goal: 

Build a model incorporating neighborhood socio-economic characteristics, 311 call details, and geo-locations to predict the outcome of 311 calls—whether they will be on time or overdue. By exploring and generating relevant features, I aim to identify an optimized classifier. 


## ML Techniques:

Supervised Learning: Various classifiers such as logistic regression, decision trees, random forests, and gradient boosting machines. Unsupervised Learning: K-Means clustering and DBSCAN based on geo and neighborhood characteristics. NLP techniques like TF-IDF and word embeddings to analyze notes and comments. 


## Data Sources: 

The three data sources were merged for the capstone project

1) 311 requests (January to June 2024) (over 163,548 records)
2) Neighborhood Characteristics (88 neighborhoods)
3) Geo Locations (latitude and longitude)

## Methodology: CRISP-DM 

![image](https://github.com/Sandysmile/Capstone/assets/20648423/4c48f9af-b92c-4a2e-94f1-25e3393aeaf8) 


### Business Understanding/Goals/Reserach 

*Stakeholders*: City management, 311 operators, and citizens.

*Pain Points*: Inefficient resource allocation, delayed response times, and suboptimal service quality.

*Value Proposition*: Transform 311 operations by predicting overdue calls, enabling better prioritization and resource allocation.

*Desired Business Outcome*: Timely process cases that are most likely to be overdue.

*What's Predicted?* How likely is an incoming call to be overdue?

*Current Approach:* 311 cases are currently managed without incorporating predictive insights into service outcomes.

### Business Goal/Outcome: 

1) Targeted Resource Allocation and Enhanced Operation Efficiency
   By predicting which 311 calls are most likely to be overdue, we can prioritize high-priority cases, ensuring that the most critical issues receive timely attention. This targeted approach leads to more effective use of city resources and improved response times.

3) Improved Service Quality
   ML-driven predictive analytics can segment calls by urgency and complexity, enabling more precise resource allocation. This ensures that complex and urgent cases are handled promptly, enhancing overall service quality and citizen satisfaction.

Proposed Enhancement Using ML:
By integrating predictive analytics, we can better anticipate which cases are likely to be overdue, allowing us to prioritize and allocate resources more effectively. This proactive approach aims to enhance service efficiency and improve overall satisfaction.


### Business Reserach for Feature Engineering

1) Neighborhood
Geographical Affiliation: 311 calls are inherently associated with specific locations or neighborhoods.
Clustering in Deteriorating Areas: 311 calls tend to cluster in neighborhoods with deteriorating physical conditions and lack of services.
Call Volume and Issue Severity: A higher number of calls in a neighborhood indicates greater intensity and severity of the issues.

![image](https://github.com/Sandysmile/Capstone/assets/20648423/8b9878d3-e3ae-4a32-8b64-884f46936822) 


![image](https://github.com/Sandysmile/Capstone/assets/20648423/bcd58ad1-6d7d-4cad-97d2-44fedb66c0d6) 


![image](https://github.com/Sandysmile/Capstone/assets/20648423/c5bbc932-ba16-4a70-8236-a21b708c5188) 


![image](https://github.com/Sandysmile/Capstone/assets/20648423/de4e6f7b-0acc-4ac2-bbec-a78fc0179f99) 





3) 311 Calls
   
![image](https://github.com/Sandysmile/Capstone/assets/20648423/f2be828f-cd6d-4793-81c3-f00bdbfe33fa) 



Type of Issue: Infrastructure-related issues typically take longer to resolve compared to administrative ones.
Call Patterns and Trends: Analyzing the patterns and trends in call types to understand the nature and recurrence of issues. Recurrent Incident Address: An increase in calls for the same address highlights the recurring nature of problems.
Case Resolution Complexity: The resolution time of a case indicates its complexity, where Natural Language Processing (NLP) can analyze comments to determine this.
Sentiment Analysis: Sentiment analysis of comments can provide insights into public sentiment and the urgency of issues.

![image](https://github.com/Sandysmile/Capstone/assets/20648423/6d184a3a-cc78-418a-97c3-84f1e2e0abcf) 


4) 311 Operations (Demand and Supply)
   
Service Level Agreement (SLA) Indicators: A higher volume of calls within SLA for the same type of issue suggests effective service and issue sensitivity.
Business Hours Impact: Cases submitted outside business hours are more likely to be overdue, with weekends and holidays following in likelihood. 

![image](https://github.com/Sandysmile/Capstone/assets/20648423/b7969e25-024f-48c3-a89f-d3706ca62a02) 



5) Call Volume Impact: High call volume can impact the operational capacity to address issues promptly.
   
Operational Capacity: Evaluating the capacity of personnel working on 311 calls, including the impact of after-hours service on call resolution times.

6) 311 Overall Reponse Trends
Historical Response Patterns: Understanding historical response times for different issue types helps in predicting future service levels. Temporal Trends: Analysis of the time of week, month, etc., can reveal patterns in call volumes and service delays.

![image](https://github.com/Sandysmile/Capstone/assets/20648423/aed93260-f64e-47d7-9293-6162c0c30b1b) 

![image](https://github.com/Sandysmile/Capstone/assets/20648423/a34445a4-596f-4cd9-9145-1d72fd6e7271) 


7) Garbadge Collection
   
Garbage collection schedules and routes significantly impact the volume and distribution of related 311 calls 

![image](https://github.com/Sandysmile/Capstone/assets/20648423/191856e9-4745-4a6f-abb1-df07c8196764) 


8) Tehcnical Integration Barrior
if a case numer is larger than 10 digits. they need to integrate to another system.

Data Understandings:

This is a pilot study. Data is built from the scratch
The data is super imbalanced.

![image](https://github.com/Sandysmile/Capstone/assets/20648423/35eb2eb7-2dd8-41d6-a892-986e72112ce8) 


# Data Understanding: 

## Initial EDA for All Cases ( Closed Cases and Open Cases)

1. Handing Missing Values

2. Understand open cases to plan splitting data strategies without data leakage problem. 

3. Understand date-related columns and coverted them if appliable 

4. Check the imbalance of the dataset

4. Drop unuseful features based on my business reserach.

5. Create Features that won't cause data leakage (beflore splitting)

6. Create geo and neighborhood clusters for segment analaysis 
   Create Geoclusters and Neighborhood Clusters to understand the innate features of 311 Calls (why did I do this step before      spliting. My assumation is Geo locations are constant, so are neighborhood clusters0. they are not changes as randomely as 
   311 reported cases.

   ![image](https://github.com/Sandysmile/Capstone/assets/20648423/8849f0a2-ca14-43e4-b69d-90b04899c2e5)
   
   ![image](https://github.com/Sandysmile/Capstone/assets/20648423/eacb3ee9-32ef-4d8b-acfa-1a6198517d05)
   Findings.

   Breakthrough Points:
   Based on the cluster mapping. I choose rerun models based on neighborhood clusters due to it shows clear patterns of cases overdues. The four clusters natural division make the four subset ofs overall data more balanced than the whole dataset


Data Splitting and Modelling Steps:

Step 1: seperate the Closed Cases from open cases(without valid closing dates): Use the closed cases to create both a training (training and testing set) and a validation set. 
This allows me to train the model and evaluate its performance on known outcomes. ( Capstone Project)
Split the whole dataset into closed cases ( Trained and testing datasets) and open cases (validation dataset)


Step 2: run a basemodel using Random Forest and all classifers to identify the optimized classifer.

Step 3: run classifiers again in each of four neighborhood clusters. 



# Model Performance Comparision




# the best classifier: KNN Classifer (Why?)

1. Geographical Clustring: 311 requests often have strong spatial dependencies. similar request tend to come from nearby locations, makiing the spatial aspect a natural fit for KNN.
2. Requests with similar characteristics(type of complaints, time of year, socioeconbomic factors of neighborhoods) might be more common, and KNN natually leverages this similarity
3. KNN is relatively straightforward to implement and understand,. 





Business Inights (Stateholders)

Feature importance, KNN interpretations. 
Highlighted insights. 




Next Step and Limitations
1. i should leverage D-KCON natural classifere.
2. my computation power is limited, I can't run or hypertune models with more parameters.
3. my dataset is limited. idealy it should include the whole year of data.
4. ideally I can further validate my model using open cases. however, since some of cases are not closed yet. I can only perform it later after the capstone project.
5. More feature engineering features by chatting with 311 operators, etcs. to find more continuted features to be include the models.
6. more reiterative modelling to
7. Ideally I can include 311 satisifiction survey data. currently I don't have enough data to be considered.
8. Refine the presentation to business stateholders to show the effectiveness of the model. 

