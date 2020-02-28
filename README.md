# 0228-Snapchat-2020_Sanny-YE

I  Brief Description 

In this project, we are using the existing 560 data points provided on the snapchat website to explore the relationship between and amount spent on political ads on Snapchat along with active days, and impressions that ads have received in the United States in 2020. We found a relationship between the amount spent on advertisement on Snapchat in the U.S; however, since most of the projects are still ongoing, we failed to find a relationship between impressions and active days. 

![image](Picture1.png)

II  Outline 

Industry Question
Is there a trend in terms of investing in political ads on Snapchat in the United States? How many impressions should companies/organizations expect if budget and active days are known?

Data Question 
Are dollars spent on political ads and the number of days for which ads are active good predictors for the amount of impressions generated? What is the relationship among these variables?

Data Answer
A relationship between the amount spent on advertisement on Snapchat in the U.S. was found as the number of impressions increases by ~366 for every dollar spent on the ad. This relationship holds true for over 60% the 560 data points we have in year 2020.

Industry Answer Findings
There is a clear connection between the amount of money spent on ads on Snapchat and impressions that ads receive, so organizations can make predictions according to the regression model prior to launching the advertisement. The relationship between the number of days in which adds are active and impressions generated are still yet to be explored using data from previous years as we don’t see a significant connection between the two variables in this project.


III  Step by Step Description

1.	Extracting data from the Snapchat official website
o	Download Snapchat election advertising data for year 2020

2.	Sorting out irrelevant data 
o	Delete irrelevant columns 
o	Click “Data” and select “Filter” to delete rows that not contain the key word “United States” in the “Country Code” column in order to ensure all data are relevant
o	Find start dates and end dates, and the number of the days in between
o	Create new column named “Start”
o	=LEFT(I2,FIND(" ",I2)-1) #remove everything (specific time, etc.) after the first space in column “StartDate” and keep the rest in “StartDate”
o	Create new column named “End”
o	=LEFT(J2,FIND(" ",J2)-1) #remove everything (specific time, etc.) after the first space in column “EndDate” and keep the rest in “End”
o	Show only columns with specific dates using “Filter”

3.	Calculating days in between
o	Create new column “Days”
o	=M2-L2 #calculate days in between start date and end date for each transaction

4.	Generating linear regression function (x = amount spent on the ads; y = number of impressions) using scatter plot and trendline

5.	Running a regression analysis using Data Analysis Tool
o	Filling in data to build the regression model
o	Set Y range (dependent variable) to be “Impressions”
o	Set X range (independent variables) to be “Spent” and “Days”
o	Select to send the output to worksheet called “regression”

6.	Analyzing data based on the linear regression function and data generated from the multi-linear regression model
o	Simple linear regression- impressions associated with dollars spent on political ads (x = amount spent on the ads; y = number of impressions)
o	y = 366.33x + 13854, with R2 = 0.61, slope = 366.33, and intercept = 13854
o	Calculate standard error Std_error = 2315807 (counts of impressions)
o	Since the R2 value is only 0.61 and the standard error is approximately 2,315,807 counts of impressions, we can conclude that amount spent on the ads alone is a good predictor of the impression. If we want to explore better predictors of the impressions generated from the political ads, we may need to take other independent variables like days that the ads are active into accounts
o	Multiple linear regression- impressions associated with both dollars spent on political ads and the number of days for which ads are active (independent variables: amount spent & active days; dependent variable: impression generated)
o	Since p-values of the active days (0.345) is more than 0.05, this variable is not significant. Thus, we need to delete this column and rerun the analysis
o	The new analysis shows similar results as in the simple linear regression model
    The R2 value (~.61) is the same as described in the simple linear regression analysis, which indicates that this model describes approximately 61% of our data.
o	The significance F (how likely that coefficients are not useful in terms of predicting our dependent variable) is approximately 3.374E-116, which is very close to 0. Thus, there is approximately 0 chance that our coefficients are not helpful to predict. In other words, our coefficients are significant.

  7.	Generating results
o	According to the regression model, impression = 13853.55 + 366.33(spend).
8.	Make predictions for the future 
o	For a given amount spent on political ads on Snapchat in the U.S., we can predict the number of people who watch the ads by using the equation above


IV  Conclusion

Based on the regression model, we found a relationship between the amount spent on advertisement on Snapchat in the U.S. as the number of impressions increases by ~366 for every dollar spent on the ad. This relationship holds true for over 60% the 560 data points we have generated in year 2020. This result intuitively makes sense because the more organizations spend on an ad, the broader the ad spreads and more people might watch the ad. Surprisingly, we found that number of days in which ads are active does not have a significant impact on the amount of impressions received. This might be due to the limitation of data we have (since the year 2020 has just started) or inaccurate data points.


V  Website Links to Data Sources

1)	https://www.snap.com/en-US/political-ads/
