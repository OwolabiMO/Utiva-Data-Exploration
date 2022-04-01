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
    
```SQL
SELECT CASE 
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
   SELECT countries, 
   	  SUM(profit) AS profits
 FROM international_breweries
 WHERE years = 2019
 GROUP BY 1
 ORDER BY 2 DESC
 LIMIT 2
 
 ```
 
    -- Help him find the year with the highest profit.
  ```SQL
 SELECT years,
 	SUM(profit) AS revenue
 FROM international_breweries
 GROUP BY 1
 ORDER BY 2 DESC;
 ```
 
    -- Which month in the three years was the least profit generated?
  ```SQL
    SELECT months,
 		SUM(profit) AS revenue
    FROM international_breweries
    GROUP BY 1
    ORDER BY 2 ASC;
```

    -- What was the minimum profit in the month of December 2018?
  ```SQL
    SELECT  months,
	    profit
    FROM international_breweries
    WHERE months = 'December' AND years = 2018
    ORDER BY 2 
    LIMIT 3;
```  
     
     
     --  Compare the profit in percentage for each of the month in 2019
     
   Three consideration were taken into place which were;
   
   1. percentage for the months(which was diveided by the total sum of the year
   2.  Grouped by the 12 months in the year 2019
   
     ```SQL
     SELECT months, 
            ((profit_per_month * 100.00)/(SELECT SUM(profit)
     FROM international_breweries
     WHERE years = 2019)) AS percent_profit			
     FROM(
     SELECT months,
		SUM(profit) as profit_per_month
     FROM international_breweries
     WHERE years = 2019
     GROUP BY 1)AS sub1;
     ```
     
     

