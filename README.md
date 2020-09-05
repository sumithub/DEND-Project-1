### Introduction
This project creates a user activity data model for a music streaming app called Sparkify. The model is optimized to run queries for understanding what songs users are listening to. This model is created in Postgres database by definig facts and dimension tables following STAR schema methodology.

The ETL process imports data in JSON format present under song_data and log_data respectively.

### Database schema design and ETL process
The ETL scripts reads files containing data in JSON format having song and user activity data. After reading the files, the process inserts records in their respective tables as defined below.

#### Fact Table
- `songplays` records in log data associated with song plays

#### Dimension Tables
- `users`: users in the app
- `songs`: songs in music database
- `artists`: artists in music database
- `time`: timestamps of records in songplays broken down into specific units 

#### Files in repository
There are 4 script files used in this project:

- `create_tables.py` drops and creates tables.

- `etl.ipynb` reads and processes a single file from song_data and log_data and loads the data into the tables. This file runs as Jupyter notebook, that utilizes Pandas and psycopg2 postgres client library to read and insert data in tables.

- `etl.py` reads and processes files from song_data and log_data and loads them into the tables. 

- `sql_queries.py` contains all sql queries to create and drop tables. This script is imported into above three files for creating and inserting records in the tables.

#### How to run the python scripts
Python scripts can be run from terminal by executing python file_name.extension in terminal. For ex: to run create_tables.py type `python create_tables.py` in terminal and enter.
