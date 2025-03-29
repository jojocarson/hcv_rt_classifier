## Machine learning to monitor national trends in hepatitis C virus reinfection and treatment failure retreatments

The treatment of hepatitis C virus (HCV) infection has evolved considerably with the development of direct-acting antiviral (DAA) therapies that are well-tolerated and yield high cure rates (≥95%). However, a small proportion of those treated will have virological failure while others may become reinfected. Retreatment of reinfection and virological failure is essential to prevent transmission, liver disease progression and HCV-related mortality. 

In Australia, there is unrestricted access to government subsidized DAAs that can be prescribed by any medical practitioner, with no restrictions on the prescribing of retreamtent. While treatment uptake was initially greatest among older individuals with advanced disease (ie with higher risk of virological failure), there has been increasing treatment uptake among youunger people who inject drugs and people who are incarcerated (ie with higher risk of reinfection). 

All dispensation of DAAs is reported through the Australian Pharmaceutical Benefit Scheme (PBS), including retreatment dispensation. The PBS provides high-coverage, structured information on patient demography and pharmacy dispensing however this data is collected for administrative purposes and lacks clinical granularity. Reasons for retreatment are important for assessing HCV elimination strategies but are not captured in the PBS data.

The REACH-C study is a national cohort of individuals receiving DAA treatment through the PBS that reported details of retreatments, including the retreatment reason. For this analysis, we used retreatment data from REACH-C to train a machine learning model to classify retreatments in PBS data as retreatment for reinfection or retreatment for virological failure.  

#### Trends in HCV treatment and retreatments in Australia
![PBS_HCV_TXRT_line](https://github.com/user-attachments/assets/6cb430b3-e24a-4803-ba15-304a4de7c51a)


#### Polar plot of DAA treatment and retreatment trends in Australia
![HCV_TXRT_polar_percent](https://github.com/user-attachments/assets/36cf78a4-6185-4835-8138-51dcb49c55c6)


#### Trends in in retreatments for reinfection and treatment failure in Australia
![PBS_HCV_RT_line](https://github.com/user-attachments/assets/700b027d-2ea1-4c80-b4ab-c98c4a0c4f71)

#### Polar plot of treatment, reiinfection retreatment & treatment failure retreatment trends in Australia
![HCV_TXRT_polar_count](https://github.com/user-attachments/assets/5f3d7a2f-a644-44ea-b676-014466b85eb0)

#### DAA regimens used to retreat reinfection
![PBS_HCV_RI_daa](https://github.com/user-attachments/assets/57a194b4-93f6-4046-b2c1-6698c2288dd9)

#### DAA regimens used to retreat treatment failure
![PBS_HCV_TF_daa](https://github.com/user-attachments/assets/a350569b-a849-4214-a532-04d807c04ac8)


### Trends in retreatment for reinfection by Australian state or territory
![PBS_HCV_RI_state](https://github.com/user-attachments/assets/f92424ed-2388-4b60-990d-f039fa13b373)

### Trends in retreatment for treatment failure by Australian state or territory
![PBS_HCV_TF_state](https://github.com/user-attachments/assets/65aa653b-433e-45d0-8ced-dc53197293bc)

### Contents
##### 01. Code for random forest classifier with nested cross validation
##### 02. Code for gradient boosting classifier with nested cross validation 
##### 03. Code for obtaining predictions and computing bootstrapped CIs

### Contributors
Joanne Carson <br> 
Sebastiano Barbieri <br> 

### Contact Information
For any question regarding the code or the model please email to: jojocarson@protonmail.com
