# Improve City 311 Services Using ML/AI: Predicting Overdue 311 Calls





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


Business Understanding:
Stakeholders: City management, 311 operators, and citizens.

Pain Points: Inefficient resource allocation, delayed response times, and suboptimal service quality.

Value Proposition: Transform 311 operations by predicting overdue calls, enabling better prioritization and resource allocation.

Desired Business Outcome: Timely process cases that are most likely to be overdue.

What's Predicted: How likely is an incoming call to be overdue?

Current Approach: 311 cases are currently managed without incorporating predictive insights into service outcomes.

Business Goal/Benefits: Targeted Resource Allocation:
Enhanced Efficiency:

By predicting which 311 calls are most likely to be overdue, we can prioritize high-priority cases, ensuring that the most critical issues receive timely attention. This targeted approach leads to more effective use of city resources and improved response times.

Improved Service Quality: ML-driven predictive analytics can segment calls by urgency and complexity, enabling more precise resource allocation. This ensures that complex and urgent cases are handled promptly, enhancing overall service quality and citizen satisfaction.

Proposed Enhancement Using ML:

By integrating predictive analytics, we can better anticipate which cases are likely to be overdue, allowing us to prioritize and allocate resources more effectively. This proactive approach aims to enhance service efficiency and improve overall satisfaction.

Business Reserach
Neighborhood
Geographical Affiliation: 311 calls are inherently associated with specific locations or neighborhoods.

Clustering in Deteriorating Areas: 311 calls tend to cluster in neighborhoods with deteriorating physical conditions and lack of services.

Call Volume and Issue Severity: A higher number of calls in a neighborhood indicates greater intensity and severity of the issues.

311 Calls
Type of Issue: Infrastructure-related issues typically take longer to resolve compared to administrative ones.

Call Patterns and Trends: Analyzing the patterns and trends in call types to understand the nature and recurrence of issues. Recurrent Incident Address: An increase in calls for the same address highlights the recurring nature of problems.

Case Resolution Complexity: The resolution time of a case indicates its complexity, where Natural Language Processing (NLP) can analyze comments to determine this.

Sentiment Analysis: Sentiment analysis of comments can provide insights into public sentiment and the urgency of issues.

311 Operations (Demand and Supply)
Service Level Agreement (SLA) Indicators: A higher volume of calls within SLA for the same type of issue suggests effective service and issue sensitivity.

Business Hours Impact: Cases submitted outside business hours are more likely to be overdue, with weekends and holidays following in likelihood.

Call Volume Impact: High call volume can impact the operational capacity to address issues promptly.

Operational Capacity: Evaluating the capacity of personnel working on 311 calls, including the impact of after-hours service on call resolution times.

311 Overall Reponse Trends
Historical Response Patterns: Understanding historical response times for different issue types helps in predicting future service levels. Temporal Trends: Analysis of the time of week, month, etc., can reveal patterns in call volumes and service delays.

Garbadge Collection
Garbage collection schedules and routes significantly impact the volume and distribution of related 311 calls

Tehcnical Integration Barrior
if a case numer is larger than 10 digits. they need to integrate to another system.
