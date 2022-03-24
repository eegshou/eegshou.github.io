---
layout: post
title:      "Analyze SyriaTel Customer Data for Suggestions"
date:       2022-03-23 23:18:38 -0400
permalink:  analyze_syriatel_customer_data_for_suggestions
---

In this project, I tried to find the features that are significantly related to the churn of customers for SyriaTel service. To this end, I have both analyzed individual features with respect of the churn and built binary classification models for prediction of customer's churn label. 

The data is SyriaTel Customer Churn![](https://www.kaggle.com/becksddf/churn-in-telecoms-dataset) with the file bigml_59c28831336c6604c800002a.csv

First, I loaded the data to checked the potential features, and found:
1) There are 20 features and one target, i.e., churn, and no missing data from all columns
2) A total of 3333 entries
3) Data types of several columns need to be changed


The first one is the histogram plot, see the following image as an example of the histogram of the house price in project 2:
![](https://raw.githubusercontent.com/eegshou/dsc-phase-2-project/mvp/Figs/Price_histogram.png)


The histogram is a bar plot with each bar indicates the number of values belonging to a specific range of values. The histogram could tell us the distribution of all values, e.g., “symmetric”, “skewed left” or “right”, “unimodal”, “bimodal” or “multimodal”. The above figure indicates the price is skewed right. It also could tell us which value range have more data. Based on the histogram plot, we could know what’s the approximate distribution of the data, e.g., normal or not, and do subsequent data processing.

The second one is the boxplot, see the following image as an example of the boxplot of price for the houses with different number of bedrooms in project 2:
![](https://raw.githubusercontent.com/eegshou/dsc-phase-2-project/mvp/Figs/boxplot_price_bedrooms.png)


The boxplot is still a bar plot, which is often used to visualizaiton the values belong to different groups with each group as a bar, e.g., the price values of the house with different number of bedrooms. The boxplot directly viusalize several summary statistics, i.e., the minimum, the maximum, the sample median, the first (Q1) and third quartiles (Q3), as well as the outliers. Based on the interquartile range (IQR) as Q3-Q1, the minimun and maximun are defined as Q1-1.5 * IQR and Q3 + 1.5 * IQR, respectively. And the values beyond the range from the minimun to maximun are the outliers. Again, the boxplot can tell us the distribution of data, e.g., it is a normal distribution if Q1 and Q3 are symmetric with respect to the median.

Based on the characteristics of the data and the project goal, we should choose proper visualization methods for different types of data.