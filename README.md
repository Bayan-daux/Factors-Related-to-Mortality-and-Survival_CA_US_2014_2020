# Lifestyle Factors Related to Mortality and Survival, 2014 - 2020

*Group members: Bayan Bahloul, Caelan Doherty, Mouad Lachhab, Ryan Lerner & Miaomiao Shen*

## Overview 

Age of death is almost impossible to predict for a variety of reasons. Death can happen in an instant, but it also commonly comes naturally through old age. However, when someone dies of old age, they don't all die at the same exact age. There are many factors that can influence a person's age of death or their life expectancy. Life expectancy is generally intended to estimate the average number of years that a person might expect to live [1]. For this analysis, we are going to explore whether there is a relationship between various factors such as sex, ethnicity, country of birth, education level, marital status and veteran status. This analysis will specifically focus on the state of California, given that this state is both heavily populated and diverse. Focusing on just one state can also help to control for less tangible factors such as happiness, technology levels and environmental conditions.  

## Data Source: 

The data used in the analysis reflects information collected and transformed by Viral Records Business Intelligence System (VRBIS) for the State of California in the years 2014–2020. This death data is derived from information entered on death certificates for California residents [2]. 

The income data in this analysis is derived from the United States Census Bureau American Community Survey (ACS) Data for the State of California by county [3]. The ACS does not produce income level information specifically for mortality records, but does contain median income levels for the overall population. Pooling this information with the data from 2014–2020 might provide additional context to estimate life expectancy. 

The death data with underlying causes of death across the states for all U.S. counties is derived from the Centers for Disease Control and Prevention. Data are based on death certificates for U.S. residents [4]. 

## ETL Process

We used python’s Pandas to load the downloaded data. After closely looking at the columns, we decided the drop the columns, ‘Type_of_Event’, ‘Residence_or_Place_of_Death’ 
‘Last_Data_Refresh’, because they don’t bring any valuable information to this analysis.
 
The dataset had all values under 11 as ‘<11’, which is a problem if we want to perform some arithmetic or comparative operation on the data. Therefore, we needed to parse this value on an “int”. Our solution in this case was to average the value to 6 in order to ensure that the death totals were all numerical/graphable. We chose this default value because there are many instances in the table where the death count equals zero. Because 0 did exist in some rows, we could understand '<11' to be greater than 0 and less than 11. Therefore, 6 seemed like an appropriate compromise to place between these two values. 
 
For The ethnicity data, the dataframe had race_ethnicity have “Non-Hispanic” attached to every Non-Hispanic ethnicity. To simplify the data, we used regex drop the “Non-Hispanic” label attached to all non Hispanic ethnicities. 
 
For each table, we renamed the death record column to not confuse the numbers when we will use more than one criteria in a dashboard.
 
We also created a table that keeps the total number of deaths, not aggregated by any characteristic. 
 
We created a table that keeps the total number of populations during the same years and how that population breakdown by county, after downloading the data we dropped the years that were outside of scope of this analysis. 
 
We made a table that shows the counties list and each county’s correspondent surface, and merged it with a table that shows if that county is considered to be a rural, urban or suburban county.
 
After the cleaning process, the dataframes were exported into a csv file that would be later used to populate our SQL database.


## Methodology:

*There will be several stages to achieve the goal of predicting life expectancy in California.

*First, we will use the Viral Records data from CA to estimate the mortality rate for each age group by county in years 2014-2020 respectively. We would then estimate the overall mortality rate in CA, and with the collaboration of the U.S. census data, compare this to the mortality rate across the U.S in the years 2014–2020 respectively. 

*Second, we will analyze the relationship between several demographic factors (sex, race/ethnicity, country of birth, education, marital status, veteran status, and income) and the mortality rate of each age group in the years 2014–2020. With this data, we can predict the trend of mortality rates across the years in CA, and by county. Additioanlly, we would use statistical modelling that includes all the possible factors to predict the life expectancy in CA. There will also be limitations and challenges posed by the data with the possibility of bias, which will be referenced in the final report.

*Lastly, we will aim to find the leading cause of death (top 10) for each age group in CA, and by county. This information can be compared to the leading cause of death estimated by the CDC [5]. For 2020, this question can be further analyzed to understand the effect of COVID on the mortality rate compared to other years in CA.

## Machine Learning Model:

*For the initial analysis, we are going to use a Multiple Linear Regression Model to predict the linear relationship between the dependent variable (age of death) and the  independent variables (sex, race/ethnicity, country of birth, education, marital status, veteran status, and income). This is the best model for us to use because it models a linear relationship between a dependent variable and several independent factors. 

*The linear regression analysis will help us to better understand the effect of the dependent variable on the independent variable, and which independent variables have the strongest impact on life expectancy. This model will also help us to predict trends and future values.

*For this analysis, we are trying the determine whether each factor will have an effect on the age of death in order to better predict the age when the value of dependent variables change. 

*Based on further analysis, decision trees and random forest models might also be needed to create a better model in predicting life expectancy. 




## Reference

1.	Arias E. United States life tables, 2008. National Vital Statistics Reports; vol 61 no 3. Hyattsville, MD: National Center for     Health Statistics. 2012. Available from: https://www.cdc.gov/nchs/data/nvsr/nvsr61/nvsr61_03.pdf.
2.	California Department of Public Health Vital Records Data and Statistics, VSB Data and Statistics (ca.gov) https://www.cdph.ca.gov/Programs/CHSI/Pages/California-Vital-Data.aspx
3.	United States Census Bureau, American Community Survey Data, American Community Survey Data (census.gov)        https://www.census.gov/programs-surveys/acs/data.html
4.	Centers for Disease Control and Prevention, CDC WONDER, Underlying Cause of Death, 1999 – 2019, Underlying Cause of Death,1999-2019 Request (cdc.gov) https://wonder.cdc.gov/controller/datarequest/D76;jsessionid=966B85BC1ED23DE79066DD928653
5.	Centers for Disease Control and Prevention, National Center for Health Statistics, Leading Cause of Death, NVSS - Leading Causes of Death (cdc.gov). https://www.cdc.gov/nchs/nvss/leading-causes-of-death.htm

## Communication Protocols

The following collaborative tools are used to facilitate communication and sharing among team members:

•	Slack For streamline communication, using a private Slack channel as the main communication platform. Beside using it for real-time communication between members, its also to share links for resources, schedule meetings, and general announcements. 
•	Zoom For virtual meetings and to share video and screen content between members. It serves as main platform for team to brain, make mutual decisions, give updates on ongoing tasks, and discuss future ones.
•	Google Documents for team members to take notes, edit, and comment in real time. Also, to keeps record of meetings, assign tasks and track project milestones and deadlines. 
•	GitHub for data repositories that also provide version control, multiple branches, and ability to merge and update. Also serve as the project archives as it allows for all team members permanent access to the project and its resources.

