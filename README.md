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



Lastly in this section, it is important to import the csv file into already created database (international_breweries). I navigate to database and right click to import/export. During this process of importing the data, i clicked the following fields:

- Format field: select csv here (Comma seperated values) since the file was in a csv format.
- Delimiter field: Determine the delimiter as it is in a csv format
- Header: Select header which turns green (Yes) because the csv file has header.

<img width="705" alt="Screenshot 2022-03-20 at 21 13 52" src="https://user-images.githubusercontent.com/62305424/159184323-2f07310a-2617-4ceb-83b0-69732ce88759.png">

    
