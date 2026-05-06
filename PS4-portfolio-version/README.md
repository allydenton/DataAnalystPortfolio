# Introduction to the Project

This project builds on earlier work completed for a Data Analysis (SIS-750) assignment focused on designing and completing a mini original research project with a slide deck as the primary deliverable.
The research examines the relationship between wealth and national power. 
Using regression analysis, the project explores how GDP per capita can relate differently to unique aspects of national power. 

The analysis relies on the National Power indicators (`power_rank`, `power_index`, `military_power`, `economic_power`, and `tech_power`) from the [Global Power and Economic Indicators dataset](https://www.kaggle.com/datasets/vedantbhavsar43/global-power-and-economic-indicators-dataset). 
The Global Power and Economic Indicators was created from the [World Bank Open Data](https://data.worldbank.org/) and [REST Countries API](https://restcountries.com/) datasets. 

The approach to this project is structured by first identifying the overall relationship between `gdp_per_capita` and composite national power (`power_index`). 
The goal of this part of the project is to establish the positive relationship but also identify to key outliers.  

After establishing this overarching relationship, the project uses a regression analysis to see the relationship with each of the dimensions of power. 
Visually, the analysis uses a multi-regression visualization as to compare the relationships identified in the regression table. 

You can view the final presentation [here]().
