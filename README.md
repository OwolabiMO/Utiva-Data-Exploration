# Utiva-Data-Exploration

During the bootcamp at Utiva, we were asked to explore the data from Nigerian breweries that contains different data from other african countries. According to the mail which we received from the team lead, we are required to analytical reports so as to present to the shareholders in the annual meeting and make business decision for business development. Below is the mail received from team lead:

Mail from the Team lead--

From the international breweries data recorded for a duration of three years, you are directed to do the following analyses to aid better decision making in order to maximize profit and reduce loss to the lowest minimum. 

We are to analyse the data in three different direction 
A) Profit Analysis
B) Brand Analysis
C) Countries Analysis

Before importing the international breweries file (csv) into pgadmin, I created a database and named it international_breweries then i right click and navigated to query tool. I entered the following codes which was generated from the properties of each table colon in the file. Below is the query script written:

CREATE TABLE public. International_breweries(
 
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
    
  


To import the csv file into the query tool. I navigate to international breweries and right click to import/export. <img width="705" alt="Screenshot 2022-03-20 at 21 13 52" src="https://user-images.githubusercontent.com/62305424/159184323-2f07310a-2617-4ceb-83b0-69732ce88759.png">

    
