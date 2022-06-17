## Classification of retreatment for reinfection and virological failure among people treated with direct acting antiviral therapy for hepatitis C in national pharmacuetical dispensing administrative data 

## 00 Overview
### Background
The treatment of hepatitis C virus (HCV) infection has evolved considerably with the development of direct-acting antiviral (DAA) therapies that are well-tolerated and yield high cure rates (≥95%). However, a small proportion of those treated will have virological failure while others may become reinfected. Retreatment of reinfection and virological failure is essential to prevent transmission, liver disease progression and HCV-related mortality. 

In Australia, there is unrestricted access to government subsidized DAAs that can be prescribed by any medical practitioner, with no restrictions on the prescribing of retreamtent. While treatment uptake was initially greatest among older individuals with advanced disease (ie with higher risk of virological failure), there has been increasing treatment uptake among youunger people who inject drugs and people who are incarcerated (ie with higher risk of reinfection). 

All dispensation of DAAs is reported through the Australian Pharmaceutical Benefit Scheme (PBS), including retreatment dispensation. The PBS provides high-coverage, structured information on patient demography and pharmacy dispensing however this data is collected for administrative purposes and lacks clinical granularity. Reasons for retreatment are important for assessing HCV elimination strategies but are not captured in the PBS data.

The REACH-C study is a national cohort of individuals receiving DAA treatment through the PBS that reported details of retreatments, including the retreatment reason. For this analysis, we used retreatment data from REACH-C to train a machine learning model to classify retreatments in PBS data as retreatment for reinfection or retreatment for virological failure.  


### Methods
A total of 10,843 individuals initaited DAA treatment in the REACH-C cohort between 2016-2019, retreatment data for 320 retreatments was collected from 2016-2020. A total of 95,274 individuals initiated DAA treatment through PBS between 2016-2021, retreatment data was availabel for 7948 retreatments was collected from 2016-2022.

The models were developed and trained to predict the reason for retreatment using variables in REACH-C that were also available in the PBS data. Variables included age, gender, HIV co-infection, prescriber type, DAA class (i.e., genotype specific, pangenotypic, salvage), regimen, and duration at (re)treatment, addition of ribavirin at (re)treatment, year of (re)treatment, time between end of initial treatment and commencing retreatment, and missed dispensations (as proportion of authorised duration). Categorical variables were converted to binary dummy variables, missed doses were included as proportion of authorised duration, year (re)treatment commenced and age were included as continuous variables. Random Forest and Gradient Boosting classifiers were considered.

Because of the modest sample size of the REACH-C retreatments (n=320), we divided the data into randomized training and validation datasets using a 3 x 10-fold nested cross validation. Nested cross-validation is an approach to model hyperparameter optimization and model selection that aims to avoid overfitting. This procedure nests the k-fold cross-validation procedure for model hyperparameter optimization inside the cross-validation procedure for model selection.  In the 3 x inner loops, the score is approximately maximized by fitting a model to each training set, and then directly maximized in selecting hyperparameters over the validation set. In the 10 x outer loops generalization error is estimated by averaging test set scores over several dataset splits. The use of nested cross validation during training reduces the likelihood of overfitting to a specific subset of the training data because performance metrics are averaged across all folds of the training set. Within the nested cross validation we used GridSearchCV to exhaustively consider all hyperparameter combinations within the defined search space.  We then configured the hyperparameter search to refit a final model with the entire training dataset using the best hyperparameters found during the search. 

#### Figure 1. Nested-cross validation
![image](https://user-images.githubusercontent.com/94947907/174217111-8b436322-774a-4747-946e-26ba8976a7b7.png)


### Results
#### Table 1. Performance metrics for Random Forest and Gradient Boosting Classifiers
![image](https://user-images.githubusercontent.com/94947907/174217333-0d884123-3c51-4e71-8cb2-97ebe5a06937.png)


#### Figure 2. Six-monthly number individuals receiving first retreatment for HCV reinfection and virological failure and the total retreatment courses dispensed for HCV reinfection and virological failure  in Australia during 2016-21 with 95% confidence intervals
![rt_all_ci](https://user-images.githubusercontent.com/94947907/174217471-82479246-102c-47fb-84dd-04e437818db4.png)


#### Figure 3. Boostrapped confidence intervals for model predictions for first retreatment and total retreatment
![bootstrapCI_github_proportion1](https://user-images.githubusercontent.com/94947907/174217530-44b3eae2-281d-4bd3-8f18-7b85143a9437.png)![bootstrapCI_github_proportion](https://user-images.githubusercontent.com/94947907/174217537-e0fa7312-2992-47b5-9776-dd0087f90de4.png)

### Contents
##### 01. Code for random forest classifier with nested cross validation
##### 02. Code for gradient boosting classifier with nested cross validation 
##### 03. Code for obtaining predictions and computing bootstrapped CIs

### Contributors
Joanne Carson <br> 
Sebastiano Barbieri <br> 
Greg Dore <br> 
Gail Matthews

### Contact Information
For any question regarding the code or the model, please send an email to: jcarson@kirby.unsw.edu.au 
