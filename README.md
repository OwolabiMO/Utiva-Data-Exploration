# UTIVA DATA EXPLORATION

This project analyses data from the International breweries record in western Africa between 2017 and 2019. The purpose of this analysis is to get insights from the beer consumption in the regions, number of brands that are in high demand and countries analysis. 

This dataset was source from Utiva as a capstone project after learning SQL. This dataset contain various information from Janauary 2017 to December 2019.

> Tools used for this analysis includes microsoft excel which was in a csv format and use when importing file into the database.Postgres Admin was used for data exploration using SQL queries .

## STATEMENT OF BUSINESS TASK

This data provides an analysis on the profits made during the year and the beer consumption between the regions in Africa. An it also proffer recommendations on how these regions can increase profits between brand . 

## DESCRIPTION OF THE DATA SOURCE USED

The dataset was taken from [here](https://import.cdn.thinkific.com/507876/courses/1431816/DSF_InternationalBreweriesSQLCapstoneProject-210714-091303.pdf)
The data was reported by each country in the record and the information is only accurate as provided by each country. The dataset was downloaded in a csv format and were loaded into pg-admin.

Before importing the international breweries file (csv) into pgadmin, I created a database and named it international_breweries and run the query below to create the columns. 

     -- CREATE TABLE public. International_breweries(
 
     sales_id integer,
   
     sales_rep character varying COLLATE pg_catalog."default",
 
     emails character varying COLLATE pg_catalog."default",
  
     plant_cost integer,
 
     unit_price integer,
 
     quantity integer,
 
     cost integer,
 
     profit integer,
 
     countries character varying COLLATE pg_catalog."default",
 
     region character varying COLLATE pg_catalog."default",

     years integer

     )
   
   After running the query code, i navigated to left side of pgadmin to see if the tables exist in the database(international_breweries).
    
  <img width="265" alt="Screenshot 2022-03-20 at 21 06 12" src="https://user-images.githubusercontent.com/62305424/159184837-3b1e485c-de9f-4bd2-ae3d-c16973dbfcc7.png">



Lastly in this section, I import the csv file into already created database (international_breweries). I navigate to database and right click to import/export. During this process of importing the data, i clicked the following fields:

- Format field: select csv here (Comma seperated values) since the file was in a csv format.
- Delimiter field: Determine the delimiter as it is in a csv format
- Header: Select header which turns green (Yes) because the csv file has header.


   
   ### Casestudy Solutions
  
The casestudy were divided into three sections which are;

a. Profit Analysis

b. Brand Analysis

c. Countries Analysis

Profit Analysis

1. **Within the space of the last three years, what was the profit worth of the breweries, inclusive of the anglophone and the francophone territories?**

<img width="525" alt="Screenshot 2022-03-31 at 11 17 39" src="https://user-images.githubusercontent.com/62305424/161021830-5019e511-2816-40c9-98f5-e17e08f40abc.png">


<img width="299" alt="Screenshot 2022-03-31 at 20 30 41" src="https://user-images.githubusercontent.com/62305424/161125343-c542ebd9-9f1b-412f-90a7-164137e8e522.png">



2.  **Compare the total profit between these two territories in order for the territory manager, Mr. Stone made a strategic decision that will aid profit maximization in 2020.**

In here i use the case function to seperate the regions into Anglophone and francophone and i also group the profits between the two case statement.

<img width="497" alt="Screenshot 2022-03-31 at 10 48 02" src="https://user-images.githubusercontent.com/62305424/161015991-b0248411-6e14-4435-a2be-3c7ae6ae1ec6.png">

<img width="252" alt="Screenshot 2022-03-31 at 20 12 25" src="https://user-images.githubusercontent.com/62305424/161122500-3f542f9e-248d-4af3-8c66-7615763cc4f4.png">


    
    
    Answer; 
            Francophone 63,198,160
            Angophone   42,198,160




3.  **Country that generated the highest profit in 2019**

I calculated the sum of the profit and group them by the countries in which they were generated. 

<img width="392" alt="Screenshot 2022-03-31 at 20 33 54" src="https://user-images.githubusercontent.com/62305424/161125843-2f3e226e-c83c-470c-85c3-eb19617400ee.png">




<img width="230" alt="Screenshot 2022-03-31 at 20 34 18" src="https://user-images.githubusercontent.com/62305424/161125879-0f15c229-b279-4aa8-b3b4-5e49c9462f68.png">



4. **Help him find the year with the highest profit**

I did sum up the profits and then group them by years so the output of each year can be total profit generated in the years.

<img width="497" alt="Screenshot 2022-03-31 at 11 28 24" src="https://user-images.githubusercontent.com/62305424/161023955-7030fcdf-c4fe-482c-b5d0-5da662e11ccd.png">

<img width="283" alt="Screenshot 2022-03-31 at 20 36 31" src="https://user-images.githubusercontent.com/62305424/161126166-fd8581d1-a5ec-4ead-8b91-3e4cfbfab62a.png">


The year with the highest profit is 2017 which had a total of 38,503,320


5.  **Which month in the three years was the least profit generated?**

Again i had to sum up the profits and group them by the months in which they are generated. 

<img width="376" alt="Screenshot 2022-03-31 at 11 41 44" src="https://user-images.githubusercontent.com/62305424/161027031-b4a3cc30-649b-40ad-beac-f6b2f19f26ea.png">


<img width="260" alt="Screenshot 2022-03-31 at 20 40 46" src="https://user-images.githubusercontent.com/62305424/161126849-50670fa9-8927-4d81-ba25-2ae0a3f4eaf7.png">


The month that generated the least profit is April with the sum of 8,573,830



6. **What was the minimum profit in the month of December 2018?**

This question here centers around the year 2018 and the month december in which the profit was made. I specified with a where function to highlight this condition and i limited the result because of the output of the result.

<img width="431" alt="Screenshot 2022-03-31 at 11 56 29" src="https://user-images.githubusercontent.com/62305424/161029850-d47ce3af-876a-4b68-809d-b4eaf5cb06c8.png">


The least profit generated in the month of december 2018 was 38,150 and 38,200


<img width="221" alt="Screenshot 2022-03-31 at 20 43 47" src="https://user-images.githubusercontent.com/62305424/161127297-95573ea0-4adf-4a03-9c65-421e68d1dab3.png">


7. **Compare the profit in percentage for each of the month in 2019**

This analysis takes into consideration two conditions which are monthly profit and year 2019. With this i created a inner query that focus on the monthly profit and then divided it by the profit for the year.

<img width="492" alt="Screenshot 2022-03-31 at 13 17 10" src="https://user-images.githubusercontent.com/62305424/161043372-0891c13e-6a4e-43e5-8f9a-c7b55568cb56.png">
 The monthly profit which will be named profit_per_month will be multiplied by 100.00 and divided by the yearly profit. 
 
 
 The script for the yearly profit is as follows:
 


 SELECT SUM(profit)
 
 FROM international_breweries

 WHERE years = 2019. 



The query written to compare the profit for the months is seen below

<img width="562" alt="Screenshot 2022-03-31 at 13 20 32" src="https://user-images.githubusercontent.com/62305424/161043871-f27c77a5-37f7-41c2-8a31-532590049581.png">


<img width="380" alt="Screenshot 2022-03-31 at 13 24 42" src="https://user-images.githubusercontent.com/62305424/161044574-73631172-2648-4b84-b520-013fa3b0158a.png">



8. **Which particular brand generated the highest profit in Senegal?**

To get the highest profit, we have to sum the profit and group them by brand as written below;


<img width="306" alt="Screenshot 2022-03-31 at 17 10 02" src="https://user-images.githubusercontent.com/62305424/161088934-794d7cf6-2499-48e2-b2c4-88664068b6be.png">


<img width="228" alt="Screenshot 2022-03-31 at 20 47 27" src="https://user-images.githubusercontent.com/62305424/161127828-f9d4aac3-0f3b-484f-8fbe-c907bab20d77.png">


The brand with the highest profit is Castlelite which has a profit of 7,012,980


## Brand Analysis

The management want to know which brand is getting more attention from the consumers in terms of demands and profit base and also want to know the brand acceptability in the various regions. The following questions below has been drawn much attention from the management;

1. **Within the last two years, the brand manager wants to know the top three brands consumed in the francophone countries**

As you know the francophone countries here include Senegal, Benin and Togo. the image below is the query script wriiten to know the top three brands in these regions.

<img width="419" alt="Screenshot 2022-03-31 at 17 42 44" src="https://user-images.githubusercontent.com/62305424/161095725-8f34d8f2-bb6c-4a35-bea4-19c6fb7205b9.png">

<img width="285" alt="Screenshot 2022-03-31 at 19 42 53" src="https://user-images.githubusercontent.com/62305424/161117322-4609daae-249c-465e-83d7-96260a879d7c.png">



The output shows that 

      Trophy 52,899
      
      Hero   50,846
      
      Eagle Lager 50630
    
2. **Find out the top two choice of consumer brands in Ghana**

The metric i use to measure consumer brand is quantity consumed. 

<img width="425" alt="Screenshot 2022-03-31 at 19 48 05" src="https://user-images.githubusercontent.com/62305424/161118686-da35389b-50b2-4adc-b738-2fef5dbb2214.png">

<img width="295" alt="Screenshot 2022-03-31 at 19 59 32" src="https://user-images.githubusercontent.com/62305424/161120343-09d6ecb7-0528-46c8-932c-17630dc66556.png">



Answer: 
       
       Eagle lite is the most demanded brand in Ghana which has about 25,829 quantities,
        
        While Castle Lite sit at the second place with a total of 25,806 beers.
