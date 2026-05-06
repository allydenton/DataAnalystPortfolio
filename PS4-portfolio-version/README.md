# Introduction to the Wealth and Composite National Power Project

This project builds on earlier work completed for a Data Analysis (SIS-750) assignment focused on designing and executing a mini original research project with a slide deck as the primary deliverable.
The research examines the relationship between wealth and different dimensions of national power. 
Specifically, it investigates how GDP per capita relates to various measures of power across countries, including economic, military, technological, and composite indicators.

The analysis relies on the national power indicators (`power_rank`, `power_index`, `military_power`, `economic_power`, and `tech_power`) from the [Global Power and Economic Indicators dataset](https://www.kaggle.com/datasets/vedantbhavsar43/global-power-and-economic-indicators-dataset). 
The Global Power and Economic Indicators dataset is constructed from multiple sources, including the [World Bank Open Data](https://data.worldbank.org/) and [REST Countries API](https://restcountries.com/) datasets, combining economic and structural indicators to measure national power. 

The approach begins by examining the relationship between GDP per capita and composite national power (`power_index`). 
This step also helps identify notable outliers that deviate from the overall trend.

After establishing the overall relationship, the project uses separate regression analyses to examine how GDP per capita relates to each dimension of national power. 
The results are visualized using a single regression plot with three regression lines, allowing for direct comparison across models.

You can view the final presentation [here](https://github.com/allydenton/DataAnalystPortfolio/blob/5faec9d567b1d6c06a34103a73df6234610c102a/PS4-portfolio-version/PS4-Portfolio-Version.pdf).
