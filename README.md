## MANIPULATION OF THE DATA

The analysis were divided into three sections which are;

a. Profit Analysis

b. Brand Analysis

c. Countries Analysis


Firstly, In generating insights on Profit analysis, profit, countries, years and months were taking into consideration as they help get understand of the location and period. 
There are several questions that need answers in this analysis which are below:

    -- Within the space of the last three years, what was the profit worth of the breweries, inclusive of the anglophone and the francophone territories?
 
 ```SQL
 
 SELECT  countries,
 
 SUM(profit) AS profit
 
 FROM international_breweries
 
 GROUP BY 1
 
 ORDER BY 2 DESC;      

 ```

    --  Compare the total profit between these two territories in order for the territory manager, Mr. Stone made a strategic decision that will aid profit maximization in 2020.
    
``SQL
SELECT 
	CASE 
		WHEN countries = 'Nigeria' THEN 'Anglophone'
		WHEN countries = 'Benin' THEN 'Francophone'
		WHEN countries = 'Ghana' THEN 'Anglophone'
		WHEN countries = 'Senegal' THEN 'Francophone'
		WHEN countries = 'Togo' THEN 'Francophone'
	END AS territories,
	    SUM(profit)
FROM international_breweries
GROUP BY 1
ORDER BY 1;
```

   -- Country that generated the highest profit in 2019
 
 ```SQL
   SELECT countries, SUM(profit) AS profits
 FROM international_breweries
 WHERE years = 2019
 GROUP BY 1
 ORDER BY 2 DESC
 LIMIT 2
 
 ```
 
