# Life Expectancy in California, 2014 - 2020

## Overview 

Life expectancy has many different definitions based on the target analysis population. Life expectancy is generally intended to estimate the average number of years that a person might expect to live [1]. There are many factors that affect the estimated age for the target population such as gender, lifestyle, living condition, education level, etc. Nowadays, most of us are facing a variety of pressures. Due to environmental impacts coupled with climate change, the average life expectancy becomes more complicated and harder to predict.

For this analysis, we are going to use death data from the State of California (CA) to predict life expectancy by sex, race/ethnicity, country of birth, education, marital status, veteran status, and income. Additionally, we are going to identify the top 10 causes of death in CA, and investigate the similarity and discrepancy of the cause of death between CA and the U.S. across states.

## Data Source: 

The data used in the analysis reflects information collected and transformed by Viral Records Business Intelligence System (VRBIS) for the State of California in the years 2014–2020. This death data is derived from information entered on death certificates for California residents [2]. The data source also includes the cause of death. 

The income data in this analysis is derived from the United States Census Bureau American Community Survey (ACS) Data for the State of California by county [3]. The ACS does not produce income level information specifically for mortality records, but does contain median income levels for the overall population. Pooling this information with the data from 2014–2020 might provide additional context to estimate life expectancy. 

The death data with underlying causes of death across the states for all U.S. counties is derived from the Centers for Disease Control and Prevention. Data are based on death certificates for U.S. residents [4]. 

## Methodology:

There will be several stages to achieve the goal of predicting life expectancy in California. 

First, we will use the Viral Records data from CA to estimate the mortality rate for each age group by county in years 2014-2020 respectively. We would then estimate the overall mortality rate in CA, and with the collaboration of the U.S. census data, compare this to the mortality rate across the U.S in the years 2014–2020 respectively. 

Second, we will analyze the relationship between several demographic factors (sex, race/ethnicity, country of birth, education, marital status, veteran status, and income) and the mortality rate of each age group in the years 2014–2020. With this data, we can predict the trend of mortality rates across the years in CA, and by county. Additioanlly, we would use statistical modelling that includes all the possible factors to predict the life expectancy in CA. There will also be limitations and challenges posed by the data with the possibility of bias, which will be referenced in the final report.

Lastly, we will aim to find the leading cause of death (top 10) for each age group in CA, and by county. This information can be compared to the leading cause of death estimated by the CDC [5]. For 2020, this question can be further analyzed to understand the effect of COVID on the mortality rate compared to other years in CA. 

## Machine Learning Model:

For the initial analysis, we are going to use a Multiple Linear Regression Model to predict the linear relationship between the dependent variable (age of death) and the  independent variables (sex, race/ethnicity, country of birth, education, marital status, veteran status, and income). This is the best model for us to use because it models a linear relationship between a dependent variable and several independent factors. 

The linear regression analysis will help us to better understand the effect of the dependent variable on the independent variable, and which independent variables have the strongest impact on life expectancy. This model will also help us to predict trends and future values.

For this analysis, we are trying the determine whether each factor will have an effect on the age of death in order to better predict the age when the value of dependent variables change. 

Based on further analysis, decision trees and random forest models might also be needed to create a better model in predicting life expectancy. 


## Reference

1.	Arias E. United States life tables, 2008. National Vital Statistics Reports; vol 61 no 3. Hyattsville, MD: National Center for     Health Statistics. 2012. Available from: https://www.cdc.gov/nchs/data/nvsr/nvsr61/nvsr61_03.pdf.
2.	California Department of Public Health Vital Records Data and Statistics, VSB Data and Statistics (ca.gov) https://www.cdph.ca.gov/Programs/CHSI/Pages/California-Vital-Data.aspx
3.	United States Census Bureau, American Community Survey Data, American Community Survey Data (census.gov)        https://www.census.gov/programs-surveys/acs/data.html
4.	Centers for Disease Control and Prevention, CDC WONDER, Underlying Cause of Death, 1999 – 2019, Underlying Cause of Death,1999-2019 Request (cdc.gov) https://wonder.cdc.gov/controller/datarequest/D76;jsessionid=966B85BC1ED23DE79066DD928653
5.	Centers for Disease Control and Prevention, National Center for Health Statistics, Leading Cause of Death, NVSS - Leading Causes of Death (cdc.gov). https://www.cdc.gov/nchs/nvss/leading-causes-of-death.htm

