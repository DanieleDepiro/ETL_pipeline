# ETL_pipeline
## Overview
This project demonstrates the creation of an automated ETL pipeline using Python and pgAdmin4 database. It involves scraping data from the Zalando website, cleaning it, and storing it into a CSV file, which is then saved into the pgAdmin4 database. The entire pipeline is automated to run once every day at a chosen time.

## Motivation 
The primary goal of this project was to practically implement an ETL pipeline. In this instance, I was in search of new shoes and utilized my recent learnings to track the prices of four different shoe models I intended to purchase. 
My aim was to apply Python programming to gather data and learn efficient task automation. Additionally, it served as an exercise to enhance my understanding of HTML.

## The Project

### The E(xtract)TL

The Python libraries *requests* and *BeautifulSoup* were utilized to construct a spider for collecting the following data: Brand, Name, and Price of the shoes. The date of collection was generated by importing the *datetime* library, creating this field to monitor changes over time. Finally, the records were saved using the *csv* library.

### The ET(ransform)L

Using *pandas*, the data was transformed – in this case, specifically removing all non-numeric values from the price field. Subsequently, the CSV file was saved.

### The ETL(oad)

Establishing a connection with the pgAdmin4 database was achieved using the *psycopg2* library. Login details were imported via *configparser* from a separated .ini file to establish the connection.

### Automating the ETL pipeline

In a separate Python file, the *schedule*, *time*, and *subprocess* libraries were used to run the ETL scripts once a day.

## Conclusion
Although simple, this pipeline can be applied in numerous real-world scenarios where monitoring values over time is crucial. For instance, tracking price changes of products in an e-commerce platform or monitoring weight changes over time.

## Improvements
To enhance the process, a script could be added to send an email if the price of any item reaches the desired price point or to trigger a warning in case the script encounters an error, such as when the structure of the website being scraped changes, resulting in the spider being unable to locate the expected values.
 