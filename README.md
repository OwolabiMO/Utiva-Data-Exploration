## MANIPULATION OF THE DATA

The analysis were divided into three sections which are;

a. Profit Analysis

b. Brand Analysis

c. Countries Analysis


Firstly, In generating insights on Profit analysis, profit, countries, years and months were taking into consideration as they help get understand of the location and period. 
There are several questions that need answers in this analysis which are below:

    -- Within the space of the last three years, what was the profit worth of the breweries, inclusive of the anglophone and the francophone territories?
 
{
 SELECT  countries,
 SUM(profit) AS profit
 FROM international_breweries
 GROUP BY 1
 ORDER BY 2 DESC;      
}
