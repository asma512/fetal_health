# fetal_health

## Problem 
Fetal mortality is a major, but often overlooked, public health (MacDorman et al, 2009). The U.S. fetal mortality rate in 2019 was 5.70 fetal deaths at 20 or more weeks of gestation per 1,000 live births and fetal deaths (Gregory et al., 2021). With fetal mortality comes a higher chance of adverse maternal health outcomes, as well as a higher risk of maternal mortality. The U.S maternal mortality rate for 2019 was 20.1 deaths per 100,000 live births (Hoyert, 2019). Child mortality reduction is an important indication of human progress and is reflected in several of the United Nations' Sustainable Development Goals (Ayres De Campos et al, 2020). By 2030, the United Nations expects countries to have eliminated preventable deaths of newborns and children under the age of five, with all countries aiming to reduce under-five mortality to at least 25 per 1,000 live births (Ayres De Campos et al, 2020).

## Dataset
I used a Cardiotocography exam dataset found on Kaggle from The Journal of Maternal-Fetal Medicine. The dataset contains 2,126 rows of 22 features extracted from Cardiotocography exams which were classified by three expert obstetricians to three fetal health states which are normal, suspect, pathological. These are the target values the models will be predicting. All the other features are numerical and have their respective units.

## Exploratory Data Analysis

![image](https://user-images.githubusercontent.com/20906514/157557631-344376f4-c89e-44bb-9914-ffbb7d5efb62.png)

The target class, fetal health, is very unbalanced. About 78 percent of the fetal health outcomes observed in this dataset are Normal. The class with the second-highest frequency is the Suspect fetal health which accounts for about 14 percent and the lowest frequency is Pathological fetal health which accounts for about 8 percent. The dataset already had the target values encoded in ordinal order: Normal was 1, Suspect was 2, Pathological was 3. Ordinal encoding converts each label into integer values and the encoded data represents the sequence of labels. In this scenario, Normal indicates that the fetus is healthy so low concern, Suspect indicates the fetus should be monitored so medium concern, and Pathological indicates problematic state so high concern. Most importantly, the model could become more inclined towards learning and predicting the Normal class than the Distressed class.


## Modeling
KNN, Logistic Regression, Decision Tree, and Random Forest

The grid search random forest produced the overall best model. It has the highest recall and precision score. The most important features where abnormal_short_term_variatability and the histogram mean, min, width and mode. Just like our random forest model short term varitability of the FHR is a key feature in classifying fetal health.

Recall: 0.97
F1 Score: 0.98
Precision: 0.98

