# Project Overview.

This project consists of data modeling with Postgres and building an ETL pipeline using Python, for the purpose of creating a SQL database for analytics team of a music streaming service called Sparkify.

## Repository files

- etl.pynb - the ETL pipeline for development in a jupyter notebook
- etl.py - the final ETL pipeline as a scripy
- create_tables.py: script that drops and creates our database tables
- sql_queries.py: script which contains all PostgreSQL queries
- test.pynb - notebook used to test ETL pipeline

### Database Design.

The design  of the database employs a star schema shown below. The schema is centered aroujnd the fact table, songplays, and connects to four dimension tables: artists, songs, users and time. 

![Schema](image/erm.png)

The songplays table relates to the primary keys of each dimention table - allowing for SQL joins for songplays table on song_id, artist_id, user_id and start_time, respectively.



### ETL (pipeline).

The data is currently stored in raw JSON logs and metadata files in the directory `data`.

The ETL pipeline processes through the raw JSON files and extracts the relevant data for each table. The data is then inserted appropriately into each table in the PostgreSQL database, if it is not already present.


## Running the Project

1. Run create_tables.py from CLI to create tables and set up the database
2. Run etl.py from CLI to process and insert data into the database
