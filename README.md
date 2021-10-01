# Project 1: Data Modeling with Postgres!

## Project Description

A startup called Sparkify wants to analyze the data they've been collecting on songs and user activity on their new music streaming app. The analytics team is particularly interested in understanding what songs users are listening to. Currently, they don't have an easy way to query their data, which resides in a directory of JSON logs on user activity on the app, as well as a directory with JSON metadata on the songs in their app.

They'd like a data engineer to create a Postgres database with tables designed to optimize queries on song play analysis, and bring you on the project. Your role is to create a database schema and ETL pipeline for this analysis. You'll be able to test your database and ETL pipeline by running queries given to you by the analytics team from Sparkify and compare your results with their expected results.


## Database design.

This database constitutes a recollection of user activity while listening to music in Sparkify, this could enable to gain insights on trends, personal preferences, and even possible recommendations. This data could be used to explore new features, such as song recommendations, in the startup and ultimately improve the user experience. 

## ETL pipeline.

The database schema and ETL pipeline was designed taking into mind the raw data, the tables respect the original format of the data to make the ETL process easier. This is why the Artist's and Song's Ids are kept as strings and gender is keep as a single char. I avoided to set the primary key constraint as there are repeating artists and songs ids, but these could be solved during the ETL Pipeline. In terms of the ETL pipeline, the process is quite simple, as we read the files and do simple transformations to ensure the data types for each table.

## Project Files

## How to run the Project
