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
   

Lastly in this section, I import the csv file into already created database (international_breweries). I navigate to database and right click to import/export. During this process of importing the data, i clicked the following fields:

- Format field: select csv here (Comma seperated values) since the file was in a csv format.
- Delimiter field: Determine the delimiter as it is in a csv format
- Header: Select header which turns green (Yes) because the csv file has header.


For further view into data into Data Manipulation and recommendation **click here


```
{
  "firstName": "John",
  "lastName": "Smith",
  "age": 25
}
```
