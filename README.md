# Utiva-Data-Exploration

During the bootcamp at Utiva, we were asked to explore the data from Nigerian breweries that contains different data from other african countries. According to the mail which we received from the team lead, we are required to analytical reports so as to present to the shareholders in the annual meeting and make business decision for business development. Here is the link to the casestudy 

https://import.cdn.thinkific.com/507876/courses/1431816/DSF_InternationalBreweriesSQLCapstoneProject-210714-091303.pdf

### Problem Statement

International Breweries want us to use the data to answer a few simple questions about the customers and regions  especially about their

A) Sales pattern

B) Profits from regions

C) Which brand is the most favourite.

In addition the management of International Breweries plans to use the analysis of this maximise profit and reduce loss within it regions.

### Creating Database on Pgadmin
Before importing the international breweries file (csv) into pgadmin, I created a database and named it international_breweries then i right click and navigated to query tool. I entered the following query script which was generated from the properties of each table colon in the file. Below is the query script written:

-- CREATE TABLE public. International_breweries(
 
 sales_id integer,
   
 sales_rep character varying COLLATE pg_catalog."default",
 
 emails caharacter varying COLLATE pg_catalog."default",
  
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

<img width="705" alt="Screenshot 2022-03-20 at 21 13 52" src="https://user-images.githubusercontent.com/62305424/159184323-2f07310a-2617-4ceb-83b0-69732ce88759.png">

   
   ### Casestudy Solutions
  
The casestudy were divided into three sections which are;

a. Profit Analysis

b. Brand Analysis

c. Countries Analysis

Profit Analysis

1. **Within the space of the last three years, what was the profit worth of the breweries, inclusive of the anglophone and the francophone territories?**

<img width="328" alt="Screenshot 2022-03-31 at 10 33 22" src="https://user-images.githubusercontent.com/62305424/161013297-42029c9f-6d80-45c6-81b8-519771513542.png">


                                 <img width="328" alt="Screenshot 2022-03-31 at 10 33 22" src="https://user-images.githubusercontent.com/62305424/161013469-f36c866b-8315-481e-a0cc-0266443a322a.png">


2.  **Compare the total profit between these two territories in order for the territory manager, Mr. Stone made a strategic decision that will aid profit maximization in 2020.**

In here i use the case function to seperate the regions into Anglophone and francophone and i also group the profits between the two case statement.

<img width="497" alt="Screenshot 2022-03-31 at 10 48 02" src="https://user-images.githubusercontent.com/62305424/161015991-b0248411-6e14-4435-a2be-3c7ae6ae1ec6.png">

 
           <img width="261" alt="Screenshot 2022-03-31 at 10 48 45" src="https://user-images.githubusercontent.com/62305424/161016050-29fa5f82-8829-40e3-98fc-0bbaee892eba.png">

    
    
    Answer; 
            Francophone 126,396,320
            Angophone   84,742,270



3.  **Country that generated the highest profit in 2019**

I calculated the sum of the profit and group them by the countries in which they were generated. 

<img width="384" alt="Screenshot 2022-03-31 at 10 58 26" src="https://user-images.githubusercontent.com/62305424/161018239-ba8a291f-9cc6-4381-8bae-435f44b04fa8.png">

                   
                   <img width="289" alt="Screenshot 2022-03-31 at 11 00 33" src="https://user-images.githubusercontent.com/62305424/161018406-02f195e8-3f2b-437f-b4c7-eafbc66584f7.png">

