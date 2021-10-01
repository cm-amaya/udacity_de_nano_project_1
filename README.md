## Discuss the purpose of this database in the context of the startup, Sparkify, and their analytical goals.

This database constitutes a recollection of user activity while listening to music in Sparkify, this could enable to gain insights on trends, personal preferences, and even possible recommendations. This data could be used to explore new features, such as song recommendations, in the startup and ultimately improve the user experience. 

## State and justify your database schema design and ETL pipeline.

TABLE songplays(
    songplay_id int, 
    start_time timestamp, 
    user_id int, 
    level text, 
    song_id text, 
    artist_id text, 
    session_id int, 
    location text, 
    user_agent text
);


TABLE users(
    user_id int,
    first_name text,
    last_name text,
    gender char(1), 
    level text
);

TABLE songs(
    song_id text, 
    title text, 
    artist_id text, 
    year int, 
    duration decimal
);

TABLE artists (
    artist_id text, 
    name text, 
    location text, 
    latitude decimal, 
    longitude decimal
);

TABLE time (
    start_time timestamp,
    hour time,
    day int,
    week int,
    month int,
    year int,
    weekday text
);


The database schema and ETL pipeline was designed taking into mind the raw data, the tables respect the original format of the data to make the ETL process easier. This is why the Artist's and Song's Ids are kept as strings and gender is keep as a single char. I avoided to set the primary key constraint as there are repeating artists and songs ids, but these could be solved during the ETL Pipeline. In terms of the ETL pipeline, the process is quite simple, as we read the files and do simple transformations to ensure the data types for each table.