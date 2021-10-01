# Project 1: Data Modeling with Postgres!

## Project Description

A startup called Sparkify wants to analyze the data they've been collecting on songs and user activity on their new music streaming app. The analytics team is particularly interested in understanding what songs users are listening to. Currently, they don't have an easy way to query their data, which resides in a directory of JSON logs on user activity on the app, as well as a directory with JSON metadata on the songs in their app.

They'd like a data engineer to create a Postgres database with tables designed to optimize queries on song play analysis, and bring you on the project. Your role is to create a database schema and ETL pipeline for this analysis. You'll be able to test your database and ETL pipeline by running queries given to you by the analytics team from Sparkify and compare your results with their expected results.


## Database design.

![alt text](https://github.com/cm-amaya/udacity_de_nano_project_1/blob/main/images/sparkifydb_erd.png?raw=true)

This database constitutes a recollection of user activity while listening to music in Sparkify, this could enable to gain insights on trends, personal preferences, and even possible recommendations. This data could be used to explore new features, such as song recommendations, in the startup and ultimately improve the user experience. 

The database schema was designed taking into mind the raw data, the tables respect the original format of the data to make the ETL process easier. This is why the Artist's and Song's Ids are kept as strings and gender is keep as a single char. The fact table is songplays, which contains the log for the user activity in the Sparkify app, the table contains the IDs to the corresponding dimension tables which are: users, songs, artists and time. 

## ETL pipeline.

 In terms of the ETL pipeline, the process is quite simple, as we read the files containing the raw data and do simple transformations to ensure the data types for each table. during the insertion into the database, it was taken into account possible duplicates and we update the given records in case of primari key conflicts. 

## Project Files

- sql_queries.py: Contains the queries in charge of droping, creating, inserting rows and selecting data from the Sparkify database.
- create_tables.py: Executes the drop and create table statements that are contained in sql_queries.py. Must be run anytime a change is made in the etl.py 
- etl.py: Script in charge of running the ETL pipeline, readind the files in data/ and loading the information to the Sparkify database.
- etl.ipynb: Jupyter notebook with a initial test of the ETL methods to use in bulk data loading. 
- test.ipynb: Jupyter notebook that allows to test the creation of the tables and ETL process by querying the tables
- ER Diagram.ipynb: Allows to create a ER diagram of the Sparkify database.

## How to run the Project

Run the **create_tables.py** script to create the database and create the corresponding tables, then run the **etl.py** to load the data, finally test the ETL process with **test.ipynb**. After running test.ipynb, restart the kernel, to close the SQL connection.

