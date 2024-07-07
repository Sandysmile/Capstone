# Enhancing City 311 Services: Predicting Potential Overdue Calls with ML 
  

![image](https://github.com/Sandysmile/Capstone/assets/20648423/ba6e4052-9a03-451b-bfd9-a3af9d4747cd)


## Project Goal
The goal of this capstone project is to build a predictive model that incorporates neighborhood socio-economic characteristics, 311 call details, and geo-locations to determine whether 311 calls will be resolved on time or become overdue. By exploring and generating relevant features, I aim to identify an optimized classifier for this prediction task.

## Machine Learning Techniques

### 1. Supervised Learning:

Logistic Regression: A statistical model used to predict the probability of a binary outcome. 

Decision Trees: A model that uses a tree-like graph of decisions and their possible consequences. 

Random Forests: An ensemble learning method that constructs multiple decision trees and merges them to get a more accurate and stable prediction. 

Support Vector Machine (SVM): A classifier that finds the hyperplane that best separates the classes in the feature space. 


### 2. Unsupervised Learning:

K-Means Clustering: A clustering method used to partition observations into k clusters based on geo and neighborhood characteristics. 


### 3. Natural Language Processing (NLP):

TF-IDF (Term Frequency-Inverse Document Frequency): A statistical measure used to evaluate the importance of a word in a document relative to a collection of documents. 

Word Embeddings: Techniques like Word2Vec or GloVe that represent words in continuous vector space. 


## Data Sources

The following three data sources were cleabed and merged for the capstone project: ( Check Jupter Notebook for Detailed Data Dictionary)

1. 311 Requests (January to June 2024): Over 163,548 records detailing various service requests.
2. Neighborhood Characteristics: Data covering 88 neighborhoods, including socio-economic indicators.
3. Geo Locations: Latitude and longitude data points for precise location-based analysis.


## Methodology: CRISP-DM 

![image](https://github.com/Sandysmile/Capstone/assets/20648423/4c48f9af-b92c-4a2e-94f1-25e3393aeaf8) 


## 1. Business Understanding 

### 1.1 Business Context/Objectives and ML Goals

#### 1.1.1 Stakeholders:

- City Management: Oversees the overall operations and resource allocation for the city services. 
- 311 Operators: Handle and manage incoming service requests from citizens. 

#### 1.1.2 Pain Points:

- Inefficient Resource Allocation: Current allocation of resources may not be optimized, leading to operation delays in service delivery. 
- Delayed Response Times: Slow response times to service requests, causing dissatisfaction among citizens. 
- Suboptimal Service Quality: Lack of predictive insights leading to a reactive rather than proactive approach. 

#### 1.1.3 Value Proposition: 

Transform 311 operations by predicting overdue calls, enabling better prioritization of service requests and efficient resource allocation. This will result in improved response times and higher citizen satisfaction levels.


#### 1.1.4 Business Objectives and Outcomes 

- Objective #1: Predict which 311 calls are most likely to be overdue.
  Outcome #1: Prioritize high-priority cases, ensuring that the most critical issues receive timely attention. This leads to more effective use of city resources and improved response times.

- Objective #2: Utilize ML-driven predictive analytics to segment calls by neighborhood characteristics.
  Outcome #2: Ensure that complex and urgent cases are handled promptly, enhancing overall service quality and citizen satisfaction.


#### 1.1.5 Aligned Machine Learning Goals

- ML Goal #1: Develop and utilize classifiers to predict the likelihood of a 311 call being overdue.
  Business Alignment: By accurately predicting overdue calls, the model enables the prioritization of high-priority cases, ensuring critical issues receive timely attention. 

- ML Goal #2: Analyze neighborhood characteristics to segment 311 calls and identify urgent and complex cases.
  Business Alignment: Using neighborhood data to segment calls ensures that complex and urgent cases are promptly handled. This enhances service quality and citizen satisfaction


### 1.2 Business Assumption and Research (for Data Understanding and Preparation(Engineering Engineering)

1.2.1 Assumption 
Geographical and Neighborhood Affiliation: 311 calls are inherently associated with specific locations or neighborhoods.

1.2.2 Research Areas 

1.2.2.1 Location (Lat and Long)

![image](https://github.com/Sandysmile/Capstone/assets/20648423/bcd58ad1-6d7d-4cad-97d2-44fedb66c0d6) 


1.2.2.2 Neighborhood Attributes

Clustering in Deteriorating Areas: 311 calls tend to cluster in neighborhoods with deteriorating physical conditions and lack of services.
Call Volume and Issue Severity: A higher number of calls in a neighborhood indicates greater intensity and severity of the issues.

![image](https://github.com/Sandysmile/Capstone/assets/20648423/c5bbc932-ba16-4a70-8236-a21b708c5188) 
![image](https://github.com/Sandysmile/Capstone/assets/20648423/8b9878d3-e3ae-4a32-8b64-884f46936822) 


1.2.2.3 Call Characteristics

- Type of Issue: Infrastructure-related issues typically take longer to resolve compared to administrative ones.

![image](https://github.com/Sandysmile/Capstone/assets/20648423/f2be828f-cd6d-4793-81c3-f00bdbfe33fa)

![image](https://github.com/Sandysmile/Capstone/assets/20648423/6d184a3a-cc78-418a-97c3-84f1e2e0abcf) 

- Call Patterns and Trends: Analyzing the patterns and trends in call types to understand the nature and recurrence of issues. 
- Recurrent Incident Address: An increase in calls for the same address highlights the recurring nature of problems.
- Case Resolution Complexity: The resolution time of a case indicates its complexity, where Natural Language Processing (NLP) can analyze comments to determine this.
- Sentiment Analysis: Sentiment analysis of comments can provide insights into public sentiment and the urgency of issues.


1.2.2.4 311 Operations (Demand and Supply)
   
- Service Level Agreement (SLA) Indicators: A higher volume of calls within SLA for the same type of issue suggests effective service and issue sensitivity.
- Business Hours Impact: Cases submitted outside business hours are more likely to be overdue, with weekends and holidays following in likelihood. 

![image](https://github.com/Sandysmile/Capstone/assets/20648423/b7969e25-024f-48c3-a89f-d3706ca62a02) 


- Call Volume Impact: High call volume can impact the operational capacity to address issues promptly.
- Operational Capacity: Evaluating the capacity of personnel working on 311 calls, including the impact of after-hours service on call resolution times.

1.2.2.5  311 Overall Reponse Trends

- Historical Response Patterns: Understanding historical response times for different issue types helps in predicting future service levels.
- Temporal Trends: Analysis of the time of week, month, etc., can reveal patterns in call volumes and service delays.

![image](https://github.com/Sandysmile/Capstone/assets/20648423/aed93260-f64e-47d7-9293-6162c0c30b1b) 

![image](https://github.com/Sandysmile/Capstone/assets/20648423/a34445a4-596f-4cd9-9145-1d72fd6e7271) 


1.2.2.6 Garbadge Collection 
   
Garbage collection schedules and routes significantly impact the volume and distribution of related 311 calls 

![image](https://github.com/Sandysmile/Capstone/assets/20648423/191856e9-4745-4a6f-abb1-df07c8196764) 


1.2.2.7 Tehcnical Integration Barrior
if a case numer is larger than 10 digits. they need to integrate to another system.


# 2 Data Understandings:

## 2.1 Initial EDA for All Cases ( Closed Cases and Open Cases)

2.1.1. Handing Missing Values

2.2.2. Understand open cases to plan splitting data strategies without data leakage problem. 

2.2.3. Understand date-related columns and coverted them if appliable 

2.2.4. Check the imbalance of the dataset
   
![image](https://github.com/Sandysmile/Capstone/assets/20648423/35eb2eb7-2dd8-41d6-a892-986e72112ce8) 

2.2.5. Drop unuseful features based on EDA analysis.

2.2.6. Create Clusters for Segment Analaysis 

- Create Geoclusters
  
- Neighborhood Clusters to understand the innate features of 311 Calls
  (why do I this clustering before data splitting?  My assumation is Geo locations are constant, so are neighborhood clusters0. they are not changes as randomely as 311 reported cases.

   ![image](https://github.com/Sandysmile/Capstone/assets/20648423/8849f0a2-ca14-43e4-b69d-90b04899c2e5)
   
   ![image](https://github.com/Sandysmile/Capstone/assets/20648423/eacb3ee9-32ef-4d8b-acfa-1a6198517d05)
   Findings.

## 2.2.7. Data Splitting, Preparing and Modelling Stratigic steps :

- Step 0: seperate the Closed Cases from open cases(without valid closing dates): Use the closed cases to create both a training (training and testing set) and a validation set. 
  This allows me to train the model and evaluate its performance on known outcomes. 

- Step 1: Split the closed cases into training and testing datasets.

- Step 2: Understand Feature Importance Analysis using a combined techine of Random Forest and Logistic Modelling

- Step 3: Run a basemodel using Random Forest and all classifers to identify the optimized classifer.

- Step 4: Run classifiers again in each of four neighborhood clusters. 

# 3 Data Prepareation (Feature Engineering)

In this project, serveral feature engineering techniques were employed to enhance the predictive power of the model. 
The techniques used include binning, target encoding, frequency encoding, and clustering using K-Means. 

3.1 New Features Created (45): ( Please See the Jupter Notebook For details)

- Higher_GarbageRisk_Flag
- Queue_target
- Queue_bin
- Status_target
- Status_bin
- Incident_Case_Type_Binned
- Incident_Case_Type_Freq
- Incident_Case_Type_Target
- SLA_Days
- SLA_Type1
- EOD_Priority
- Normalized_SLA_Days
- SLA_Category
- SLA_Urgency
- SLAdays_Overdue_Risk
- SLA_Time_Bucket
- SLA_Deviation_from_Mean
- SLA_Urgency_Index
- SLA_Short_Term_Workload
- SLA_Medium_Term_Workload
- SLA_Long_Term_Workload
- SLA_Urgency_Index_Total
- SLA_Dynamic_Workload
- Calls_Per_Address
- Calls_Per_Street
- Create_To_Close_Diff
- Creation_Flag
- Due_Flag
- Create_To_Due_Diff
- Garbage_Route_Risk_Category
- Neighborhood_Risk_Category
- Queue_Top
- Customer_SuperNeighborhood_Top
- SLA_Time_Top
- Status_Top
- Division_Top
- Create_Day_Of_Week
- Create_Month_Of_Year
- Create_Hour_Of_Day
- Due_Day_Of_Week
- Due_Month_Of_Year
- Due_Hour_Of_Day
- Geo_Cluster
- Neighborhood_Cluster

3.2. New Features Selection

Only 18 new features are included in the final dataset for modelling.

- Neighborhood_cluster
- Higher_GarbageRisk_Flag
- Incident_Case_Type_Binned
- Normalized_SLA_Days
- SLA_Dynamic_Workload
- Create_To_Close_Diff
- Creation_Flag
- Due_Flag
- Garbage_Route_Risk_Category
- Sentiment_Polarity
- Sentiment_Subjectivity
- Due_Day_Of_Week
- Technical_Interface
- Create_Day_Of_Week
- Queue_Top
- Status_Top
- Division_Top
   

3.3. NLP Features and Correlation with Target Variable
 
![image](https://github.com/Sandysmile/Capstone/assets/20648423/29ba5fb6-49b9-49b0-94b5-3457a80ee276)
   
3.4 NLP Feature Selection

None of NLP features are helpful for model consideration. 
   
3.5 Final Dataset for Modelling

![image](https://github.com/Sandysmile/Capstone/assets/20648423/20f88fea-ba4e-4378-b49f-e2926fad76d7) 


3.6 Deep EDA for Final Dataset's Features

3.6.1 categorical variables

Significant Varaibles:

- Garbage_Route_Risk_Category
  
![image](https://github.com/Sandysmile/Capstone/assets/20648423/5111baa4-5304-40ea-b65c-598494163e13)


- Due_Flag
- 
![image](https://github.com/Sandysmile/Capstone/assets/20648423/ddb7630f-6bad-4053-9e67-bcd1be2c38f4)


- Creation_Flag
- 
![image](https://github.com/Sandysmile/Capstone/assets/20648423/4289659e-2d4b-49d9-9c2e-f13f37566df5)


Incident_Case_Type_Binned 

![image](https://github.com/Sandysmile/Capstone/assets/20648423/de4b3b99-9750-4541-b8c4-dbba7b786a8f) 


- Create_Day_Of_Week
- 
![image](https://github.com/Sandysmile/Capstone/assets/20648423/ab46a5ec-9207-4105-8eeb-022e132667e4)


3.6.2. Major Findings from Cateogrocal Variables

- The timing when a case is created and its due date significantly impact the likelihood of it being overdue.

- Different types of cases have varying probabilities of being overdue, indicating that some case types are more prone to delays.

- Cases related to garbage collection exhibit higher risk factors, affecting their timely resolution.
  
3.6.2 Numerical Variables

3.6.2.1 Check and Drop Highly Correlated Neighborhood Variables

![image](https://github.com/Sandysmile/Capstone/assets/20648423/bfc419d7-62fd-4d43-a97a-845e4324bd2f) 

3.6.2.2 Correlation with Target Varaibles

![image](https://github.com/Sandysmile/Capstone/assets/20648423/6628f2e9-5ac4-4ae0-8e97-0b084afa1656)


3.6.3 Remove Outliers using Percentile

![image](https://github.com/Sandysmile/Capstone/assets/20648423/b69b598f-5fa4-4fef-9a31-462f64cb11b4) 

![image](https://github.com/Sandysmile/Capstone/assets/20648423/97ee75e3-58a4-4c5c-948e-42a16adf1572) 

![image](https://github.com/Sandysmile/Capstone/assets/20648423/96b17f3d-96f1-4500-9574-d4b549ec57cd) 

![image](https://github.com/Sandysmile/Capstone/assets/20648423/fbe935d0-9887-431f-b3d7-956b24a07aae) 



# 4. Modelling 
4.1 
# Model Performance Comparision 

![image](https://github.com/Sandysmile/Capstone/assets/20648423/04bcccd2-d73a-4ef9-ab79-013a03305ebd) 

# Model Comparision for each cluster.

![image](https://github.com/Sandysmile/Capstone/assets/20648423/6acff82a-7ce4-4fab-bc0d-c1bc356643f9) 

![image](https://github.com/Sandysmile/Capstone/assets/20648423/b0fbedd9-74af-4d1b-af23-aed64afe5a09)

# the best classifier: KNN Classifer (Why?)

1. Geographical Clustring: 311 requests often have strong spatial dependencies. similar request tend to come from nearby locations, makiing the spatial aspect a natural fit for KNN.
2. Requests with similar characteristics(type of complaints, time of year, socioeconbomic factors of neighborhoods) might be more common, and KNN natually leverages this similarity
3. KNN is relatively straightforward to implement and understand,. 

## KNN Classifer Confusion Matrix Analysis:

![image](https://github.com/Sandysmile/Capstone/assets/20648423/efcab3f4-be67-419a-95c9-0294d369590a) 
![image](https://github.com/Sandysmile/Capstone/assets/20648423/bc5d2eba-0ad8-4ee1-b2e4-93332d5203c7) 
![image](https://github.com/Sandysmile/Capstone/assets/20648423/89bdd34d-38bc-4f14-aa52-3b776ffd0b71) 
![image](https://github.com/Sandysmile/Capstone/assets/20648423/b90d314c-105a-4c92-b2cf-f913dc95b628) 


# Business Insights Overview

The following insights are based on an analysis of overdue cases across different neighborhoods in the city. Neighborhoods have been grouped into clusters to better understand the patterns and identify areas that may require focused attention.

## K-Nearest Neighbors: Key Insights

1) Cluster 1: 

High False Negative Rate: This cluster has the highest number of false negatives (1594). This means many overdue cases are not being correctly identified.
Neighborhoods in this Cluster: Brays Oaks, Briar Forest, Clear Lake, Eldridge/West Oaks, Greater Uptown, Gulfton, Memorial, Mid West, Sharpstown, Westchase.
Action Required: Increase the sensitivity of the model to correctly identify more overdue cases. Consider additional features or improved data quality for these neighborhoods.

2) Cluster 2:

Balanced Performance: This cluster has fewer false positives (190) and false negatives (311), indicating a relatively balanced performance.
Neighborhoods in this Cluster: Acres Home, Addicks Park Ten, Alief, Carverdale, East Houston, East Little York/Homestead, Fort Bend Houston, Greater Fondren Southwest, IAH/Bush, Inwood, Lake Houston, Northshore, Sunnyside, Willowbrook.
Action Required: Continue monitoring these neighborhoods but consider slight model adjustments to improve overall accuracy.


Cluster 3 

Moderate False Negatives: This cluster has a moderate number of false negatives (376), indicating some overdue cases are missed.
Neighborhoods in this Cluster: Downtown, East End, Eastside, Edgebrook Area, Eldridge/West Oaks, Harrisburg/Manchester, Meyerland Area, Museum Park, Near Northside, Northside/Northline, South Belt/Ellington, South Main, Spring Branch East, Spring Branch West, Trunkline/Uptown.
Action Required: Focus on improving recall for these neighborhoods to reduce the number of missed overdue cases.

Cluster 0 

Relatively Balanced Performance: This cluster also shows a relatively balanced performance with 206 false positives and 323 false negatives.
Neighborhoods in this Cluster: Central Southwest, Greater Heights, Kingwood Area, Magnolia Park, Near Northside, Oak Forest/Garden Oaks, Washington Avenue.
Action Required: Similar to Cluster 2, maintain current monitoring but explore opportunities for minor improvements.

Recommendations
Enhance Model Sensitivity: For clusters with high false negatives, adjust model parameters or incorporate additional features to better capture overdue cases.
Targeted Interventions: Focus interventions on neighborhoods with higher rates of missed overdue cases to ensure timely responses.
Continuous Monitoring: Maintain regular performance monitoring across all clusters to ensure the model remains effective as new data becomes available.
By addressing these points, I can improve the accuracy and efficiency of identifying overdue cases, leading to better resource allocation and more timely responses to community needs.


## finding optimal threshold for each cluser. 

![image](https://github.com/Sandysmile/Capstone/assets/20648423/634d9669-dff7-4cbf-a33c-052174be90de) 


Insights from ROC Curves for K-Nearest Neighbors by Clusters
AUC (Area Under Curve)
Cluster 1: AUC = 0.83
Cluster 2: AUC = 0.84
Cluster 3: AUC = 0.83
Cluster 0: AUC = 0.81
Clusters 1, 2, and 3 show good model performance in distinguishing between overdue and non-overdue cases. Cluster 0 has slightly lower AUC but still acceptable.

Optimal vs. Default Threshold
Optimal Thresholds:
Cluster 1: 0.29
Cluster 2: 0.29
Cluster 3: 0.29
Cluster 0: 0.20
Default Threshold: 0.5 for all clusters
Optimal thresholds are lower than the default 0.5, improving the model's ability to identify overdue cases.

True Positive Rate (Sensitivity) and False Positive Rate
Optimal thresholds increase true positive rates while maintaining reasonable false positive rates.
Red circles (optimal thresholds) are higher on the True Positive Rate axis compared to blue crosses (default threshold), indicating better recall for overdue cases.

Summary
High AUC Values: Good performance across all clusters (AUC around 0.83 to 0.84).
Lower Optimal Thresholds: Optimal thresholds are lower, enhancing model performance for overdue cases.
Improved Recall: Optimal thresholds improve sensitivity, ensuring more overdue cases are detected.

Actions
Adopt Optimal Thresholds: Implement optimal thresholds to improve overdue case detection across clusters.
Monitor False Positives: Ensure false positive rates remain acceptable while using lower thresholds.
Periodic Review: Regularly review and adjust thresholds with new data to maintain optimal performance.



Next Steps
Evaluate Precision and Recall: Compare precision and recall metrics for default and optimal thresholds to understand the trade-offs better.
Consider Business Impact: Evaluate which metric (accuracy vs. recall) aligns best with business objectives.

![image](https://github.com/Sandysmile/Capstone/assets/20648423/bb7ce0dc-dca5-46e3-87bc-17985fb7266a) 


Key Observations:
Optimal Thresholds:

Cluster 1, 2, 3: Optimal Threshold = 0.29
Cluster 0: Optimal Threshold = 0.40
The optimal thresholds for clusters 1, 2, and 3 are lower (0.29), while cluster 0 has a higher optimal threshold (0.40). This indicates that cluster 0 requires a higher probability threshold to optimize the balance between precision and recall.

Precision and Recall Trade-Offs:

Clusters 1, 2, and 3: These clusters have a relatively similar performance, with precision decreasing as recall increases. This is indicative of a typical trade-off between precision and recall.
Cluster 0: Shows a slightly different pattern, with a higher optimal threshold suggesting different dynamics in this cluster.
Performance Range:

Precision: For all clusters, precision starts high and decreases as recall increases, indicating that as the model attempts to capture more true positives, the proportion of false positives also increases.
Recall: Higher recall means more true positives are identified, but at the cost of precision.
Business Impact:
Improved Detection (Recall):

Clusters 1, 2, and 3: The similar optimal thresholds (0.29) across these clusters suggest that a unified strategy for improving detection rates (recall) can be implemented. This can lead to better resource allocation and timely intervention in these neighborhoods.
Cluster 0: Requires a different threshold (0.40), indicating the need for a tailored approach to optimize detection in this cluster. This might involve different resource management or prioritization strategies.
Managing False Positives (Precision):

Clusters 1, 2, and 3: The precision decreases as recall increases, suggesting that while more true positives are being detected, the cost of false positives increases. This trade-off needs to be managed carefully to ensure resources are not wasted on non-overdue cases.
Cluster 0: The higher threshold suggests that the model is more conservative in predicting overdue cases, which could mean fewer false positives but potentially more missed true positives.
Resource Allocation:

Unified Strategy for Clusters 1, 2, 3: Given the similar optimal thresholds, a unified approach to manage and allocate resources in these clusters could be effective.
Tailored Strategy for Cluster 0: A separate, more conservative strategy might be required for cluster 0 to manage its unique characteristics.
Periodic Review and Adjustment:

Continuous Monitoring: Regularly review and adjust the thresholds based on new data to maintain optimal performance. This ensures that the model remains effective over time and adapts to any changes in the data patterns.
Recommendations:
Adopt Optimal Thresholds: Implement the optimal thresholds for each cluster to balance precision and recall effectively.
Monitor Performance: Continuously monitor the performance of the model, especially the precision and recall trade-offs, to ensure that the balance aligns with business objectives.
Tailored Approaches: Use a unified strategy for clusters 1, 2, and 3, while adopting a tailored approach for cluster 0 to optimize resource allocation and management.
By following these recommendations, the business can improve the detection of overdue cases while managing the trade-offs between precision and recall, leading to more efficient resource utilization and timely interventions.

Feature importance, KNN interpretations. 
Highlighted insights. 


# Model Summary for Business Stakeholders

0. KNN Classifier for 311 cases
   
2. Optimal Thresholds for Predictions:

Clusters 1, 2, 3: Optimal Threshold = 0.29
Cluster 0: Optimal Threshold = 0.40
2. Performance Insights:

Unified Strategy: The similar optimal thresholds across clusters 1, 2, and 3 suggest that a unified strategy can effectively improve detection rates in these areas.
Tailored Approach for Cluster 0: The higher optimal threshold for cluster 0 indicates a need for a more conservative and customized strategy in this area.
3. Balancing Detection and Efficiency:

Clusters 1, 2, 3: As the model aims to detect more overdue cases, there is a trade-off with a higher rate of cases being flagged unnecessarily.
Cluster 0: The higher threshold helps balance the detection process, minimizing unnecessary flags but potentially missing some overdue cases.
4. Business Impact:

Enhanced Detection: Implementing optimal thresholds enhances the model's ability to identify overdue cases, ensuring timely interventions.
Efficient Resource Management: Monitoring and managing unnecessary flags to ensure resources are focused on genuine overdue cases.
Optimized Resource Allocation: A unified strategy for clusters 1, 2, and 3 and a tailored strategy for cluster 0 will optimize resource allocation and improve service quality.
5. Recommendations:

Adopt Optimal Thresholds: Implement the optimal thresholds to balance the detection and efficiency effectively.
Monitor Performance: Continuously monitor model performance to ensure it aligns with business objectives.
Tailored Approaches: Use a unified approach for clusters 1, 2, and 3, and a tailored approach for cluster 0 for optimal resource management.
Conclusion:
By leveraging predictive analytics, we can transform 311 operations to be more efficient and responsive. This approach enables targeted resource allocation, timely interventions for high-priority cases, and improved overall service quality, ultimately leading to higher citizen satisfaction.

# Important features

Important Factors Influencing Overdue 311 Cases
Key Variables:
Create_To_close_Diff
SLA_Dynamic_Workload
Due_Day_Of_Week_Thursday
Division_Top_Collections
Normalized_SLA_Days
Queue_Top_UNKNOWN
sentiment_polarity
Incident_Case_Type_Binned_Missed Garbage Pickup
sentiment_subjectivity
na_Built_1939_or_earlier
h_3_bedrooms
et_White
h_Mobile_home
Creation_Flag_Regular Case
d_Median_Age

Explanation for Stakeholders
1. Create_To_close_Diff

Impact: The time difference between case creation and closure is the most significant factor. A longer time to close a case indicates a higher likelihood of it becoming overdue.
Business Insight: Focusing on reducing the time it takes to resolve cases can significantly decrease overdue incidents.
2. SLA_Dynamic_Workload

Impact: The workload dynamic of the service level agreement (SLA) affects the likelihood of cases being overdue. Higher workloads can lead to more overdue cases.
Business Insight: Managing workloads more effectively and ensuring that SLAs are realistic and achievable can help in reducing overdue cases.
3. Due_Day_Of_Week_Thursday

Impact: Cases due on Thursdays are more likely to become overdue compared to other days.
Business Insight: Understanding patterns related to specific days can help in planning and allocating resources more efficiently to prevent overdue cases.
4. Division_Top_Collections

Impact: Cases related to top collections divisions have a notable impact on whether they become overdue.
Business Insight: Focusing on improving processes within the collections division can help in managing overdue cases more effectively.
5. Normalized_SLA_Days

Impact: The normalized number of days within the SLA impacts the likelihood of cases becoming overdue. Shorter SLAs tend to reduce overdue cases.
Business Insight: Reviewing and adjusting SLAs to ensure they are appropriately set can help in managing case timelines more effectively.
6. Queue_Top_UNKNOWN

Impact: Cases in the unknown queue have a significant likelihood of becoming overdue.
Business Insight: Identifying and addressing issues within the unknown queue can help in reducing overdue cases.
7. Sentiment Polarity

Impact: The sentiment expressed in the case description influences the likelihood of it becoming overdue. Negative sentiment may indicate more complex or urgent issues.
Business Insight: Using sentiment analysis to prioritize and address cases with negative sentiment can help in preventing them from becoming overdue.
8. Incident_Case_Type_Binned_Missed Garbage Pickup

Impact: Missed garbage pickup cases have a higher likelihood of becoming overdue.
Business Insight: Streamlining processes for handling missed garbage pickups can help in reducing overdue cases in this category.
9. Sentiment Subjectivity

Impact: The subjectivity of the sentiment in case descriptions also affects the likelihood of cases becoming overdue. Highly subjective cases may indicate more complex issues.
Business Insight: Addressing highly subjective cases promptly can help in managing and reducing overdue cases.
10. na_Built_1939_or_earlier

Impact: Cases related to buildings constructed in 1939 or earlier are more likely to become overdue.
Business Insight: Focusing on addressing issues in older buildings can help in reducing overdue cases in these areas.
11. h_3_bedrooms

Impact: Cases related to homes with three bedrooms have a notable impact on overdue cases.
Business Insight: Understanding patterns related to property size can help in resource planning and case management.
12. et_White

Impact: The ethnicity of the neighborhood (specifically areas with a higher percentage of White residents) affects the likelihood of cases becoming overdue.
Business Insight: Tailoring services to specific neighborhood demographics can improve service efficiency and reduce overdue cases.
13. h_Mobile_home

Impact: Cases related to mobile homes have a significant likelihood of becoming overdue.
Business Insight: Addressing unique issues related to mobile homes can help in managing overdue cases.
14. Creation_Flag_Regular Case

Impact: Regular cases, as opposed to special cases, have a significant impact on overdue likelihood.
Business Insight: Streamlining processes for regular cases can help in managing overall case timelines.
15. d_Median_Age

Impact: The median age of residents in a neighborhood influences the likelihood of cases becoming overdue.
Business Insight: Understanding demographic influences can help in tailoring services and resource allocation to reduce overdue cases.
Conclusion
By focusing on these key variables, the city management and 311 operators can develop targeted strategies to improve service delivery, prioritize resources effectively, and ultimately enhance citizen satisfaction.

Next Step and Limitations
1. I should leverage D-KCON natural classifere.
2. my computation power is limited, I can't run or hypertune models with more parameters.
3. my dataset is limited. idealy it should include the whole year of data.
4. ideally I can further validate my model using open cases. however, since some of cases are not closed yet. I can only perform it later after the capstone project.
5. More feature engineering features by chatting with 311 operators, etcs. to find more continuted features to be include the models.
6. more reiterative modelling to
7. Ideally I can include 311 satisifiction survey data. currently I don't have enough data to be considered.
8. Refine the presentation to business stateholders to show the effectiveness of the model. 

