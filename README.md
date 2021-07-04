# Life Expectancy Analysis

## Overview 

Life expectancy has many different definitions based on the target analysis population. Life expectancy is generally intended to estimate the expected average number of years of life remaining at a given age [1]. There are many factors that affect the estimated age for the target population, such as gender, lifestyle, living condition, education level, etc. Nowadays, most of us are facing a variety of pressures. Due to environmental impacts coupled with climate change, the average life expectancy becomes complicated and harder to predict.

For this analysis, we are going to use the death data from the State of California (CA) to predict the life expectancy by sex, race/ethnicity, country of birth, education, marital status, veteran status, and income. Additionally, we are going to identify the top 10 causes of death in CA, and investigate the similarity and discrepancy of the cause of death between CA and the U.S. across states.
## Data Source: 

The data used in the analysis reflect information collected and transformed by Viral Records Business Intelligence System (VRBIS) for the State of California in year 2014 – 2020. The death data derived from information entered on death certificates which is refreshed monthly [2]. The data source also includes the leading cause of death. 

The income level data in this analysis derived from United States Census Bureau American Community Survey (ACS) Data for the State of California by county [3]. The ACS does not produce income level information for mortality records specifically, therefore, ACS only contains the median income level data for overall population. Pooling 2014 – 2020 years of data as an additional factor that might provide estimate affect to life expectancy. 

The death data with underling cause of death across the states for all U.S. counties derived from Centers for Disease Control and Prevention. Data are based on death corticates for U.S. residents [4]. 

## Methodology:

There will be several stages to achieve the goal of predicting the life expectancy in CA. 

First, use the Viral Records data from CA to estimate the mortality rate for each age group by county in year 2014 - 2020 respectively. Estimate the overall mortality rate in CA, and with the collaboration of the U.S. census data, compare to the mortality rate across the U.S in year 2014 – 2020 respectively. 

Second, analyze the relationship between each main factor (sex, race/ethnicity, country of birth, education, marital status, veteran status, and income) and mortality rate of each age group in year 2014 – 2020. Predict the trend of mortality rate across the years in CA, and by county. Use statistical modelling that including all the possible factors to predict the life expectancy in CA. Explain the limitation and challenge posed by the data and the possibility of analyses bias. 

Last, find the leading cause of death (top 10) for each age group in CA and by county. Compare to the leading cause of death estimated by CDC [5]. For 2020, further analyze the COVID on the affection of the mortality rate compare to other years in CA. 

## Machine Learning Model:

For the initial analysis we are going to use Multiple Linear Regression Model to predict the linear relationship between the dependent variable (age) and the independent variables (sex, race/ethnicity, country of birth, education, marital status, veteran status, and income). 

The linear regression analysis will help us to better understand the affect of the dependent variable to the independent variable, and it will also help us to predicts the trends and future values. 

For this analysis, we are trying the find out whether each factor will have an affect on the age of death, in order to better predict the age when the value of dependent variables change. 

Based on further analysis, decision trees and random forests might also be needed to create a better model in predicting life expectancy. 


## Reference

1.	Arias E. United States life tables, 2008. National Vital Statistics Reports; vol 61 no 3. Hyattsville, MD: National Center for     Health Statistics. 2012. Available from: https://www.cdc.gov/nchs/data/nvsr/nvsr61/nvsr61_03.pdf.
2.	California Department of Public Health Vital Records Data and Statistics, VSB Data and Statistics (ca.gov) https://www.cdph.ca.gov/Programs/CHSI/Pages/California-Vital-Data.aspx
3.	United States Census Bureau, American Community Survey Data, American Community Survey Data (census.gov)        https://www.census.gov/programs-surveys/acs/data.html
4.	Centers for Disease Control and Prevention, CDC WONDER, Underlying Cause of Death, 1999 – 2019, Underlying Cause of Death,1999-2019 Request (cdc.gov) https://wonder.cdc.gov/controller/datarequest/D76;jsessionid=966B85BC1ED23DE79066DD928653
5.	Centers for Disease Control and Prevention, National Center for Health Statistics, Leading Cause of Death, NVSS - Leading Causes of Death (cdc.gov). https://www.cdc.gov/nchs/nvss/leading-causes-of-death.htm

