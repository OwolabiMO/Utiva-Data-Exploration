## MANIPULATION OF THE DATA

The analysis were divided into three sections which are;

a. Profit Analysis

b. Brand Analysis

c. Countries Analysis

## Profit Analysis

Firstly, In generating insights on Profit analysis, profit, countries, years and months were taking into consideration as they help get understand of the location and period. 
There are several questions that need answers in this analysis which are below:

 --  Within the space of the last three years, what was the profit worth of the breweries, inclusive of the anglophone and the francophone territories?
 
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
     
     
  -- Compare the profit in percentage for each of the month in 2019
     
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
     
     
  -- Which particular brand generated the highest profit in Senegal?
     
  ```SQL 
     SELECT brands,
	    SUM(profit) as Revenue
     FROM international_breweries
     WHERE countries = 'Senegal'
     GROUP BY 1
     ORDER BY 2 DESC;
  ```
     
 ## Brand Analysis
     
The brand analysis entails the brand usage by customers in all the regions.The questions here focus more on brands, customer and quantity. 


  -- Within the last two years, the brand manager wants to know the top three brands consumed in the francophone countries
    
  ```SQL 
    SELECT brands,
	   SUM(quantity) AS consumption
    FROM international_breweries
    WHERE countries in ('Senegal','Togo','Benin')
	AND years in (2018,2019)
    GROUP BY 1
    ORDER BY 2 DESC
    LIMIT 3;
  ```
    
    
-- Find out the top two choice of consumer brands in Ghana
   
   
   ```SQL
   SELECT brands,
	  SUM(quantity) AS consumer_choice
   FROM international_breweries
   WHERE countries = 'Ghana'
   GROUP BY brands
   ORDER BY 2 DESC 
   LIMIT 2;
   ```

  --  Find out the details of beers consumed in the past three years in the most oil reached country in West Africa.
    
    
  ```SQL
    SELECT brands,
	   region,
	   SUM(quantity) AS quantities
    FROM international_breweries
    WHERE countries = 'Nigeria'
	AND years between 2017 AND 2019
	AND brands NOT LIKE '%Malt%'
    GROUP BY 1,2
    ORDER BY 3 DESC
  ```
    
    
  -- Favorites malt brand in Anglophone region between 2018 and 2019
   
   
 ```SQL
    SELECT countries,
	   region,
	   brands,
	   SUM(quantity) as most_consumed
    FROM international_breweries
    WHERE countries in ('Nigeria','Ghana')
		AND brands LIKE '%malt%'
		AND years BETWEEN 2018 AND 2019
    GROUP BY 1,2,3
    ORDER BY 4 DESC;
   ```


-- Which brands sold the highest in 2019 in Nigeria?

```SQL
   SELECT brands,
	  SUM(profit) as profit
   FROM international_breweries
   WHERE countries = 'Nigeria'
	AND years = 2019
   GROUP BY 1
   ORDER BY 2 DESC
   LIMIT 3;
```


-- Favorites brand in South_South region in Nigeria

```SQL
   SELECT brands,
	  SUM(quantity) as Favourite
   FROM international_breweries
   WHERE region ='southsouth'
		AND countries = 'Nigeria'
   GROUP BY 1
   ORDER BY 2 DESC
   LIMIT 3;
   ```
    
-- Bear consumption in Nigeria

```SQL
   SELECT brands,
          SUM(quantity) AS beers_quantity
   FROM international_breweries
   WHERE brands NOT LIKE '%Malt'
	AND countries = 'Nigeria'
   GROUP BY 1
   ORDER BY 2 DESC
   ```

-- Level of consumption of Budweiser in the regions in Nigeria

```SQL
SELECT Region,
       SUM(quantity) AS consup_quantities
FROM International_breweries
WHERE brands = 'budweiser' AND countries = 'Nigeria'
GROUP  BY 1
ORDER BY 2 DESC;
```

-- Level of consumption of Budweiser in the regions in Nigeria in 2019 (Decision on Promo)

```SQL
SELECT Region,
       SUM(quantity) AS consup_quantities
FROM International_breweries
WHERE brands = 'budweiser' AND countries = 'Nigeria'
		AND years =2019
GROUP  BY 1
ORDER BY 2 DESC;
  ```

## Brand Analysis

The main analysis will be centered on country profit and the personnel in these countries. Sales representatives will also serve as metric in measuring number of quantities sold. 

-- Country with the highest consumption of beer.

```Sql
SELECT countries,
		SUM(quantity) AS consump_quantities
FROM International_breweries
WHERE brands NOT LIKE '%Malt%'
GROUP BY 1
ORDER BY 2 DESC
LIMIT 1
```



-- Highest sales personnel of Budweiser in Senegal

```sql
SELECT sales_rep,
       SUM(quantity) as sales
FROM international_breweries
WHERE brands = 'budweiser' 
	AND countries ='Senegal'
GROUP BY 1
ORDER BY 2 DESC
LIMIT 5;
```


--Country with the highest profit of the fourth quater in 2019

```SQL
SELECT countries,
	SUM(profit) AS profit
FROM International_breweries
WHERE months IN ('october','November','December')
	AND years = '2019'
GROUP BY 1
ORDER BY 2 DESC
LIMIT 3:
```
