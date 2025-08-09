# Sparkify ETL Pipeline

## Project Summary
This project builds an ETL pipeline for Sparkify, which is a music streaming startup. The pipeline extracts data from JSON and metadata files, transforms it into a star schema, and loads it into a PostgreSQL database. The analytics team can now query the database to analyze user listening patterns, popular songs, peak usage times, and gather other insights.

### Fact Table
- songplays: records of song plays from the log data
  - songplay_id, start_time, user_id, level, song_id, artist_id, session_id, location, user_agent

### Dimension Tables
- users: users in the app
  - user_id, first_name, last_name, gender, level
- songs: songs in the music database
  - song_id, title, artist_id, year, duration
- artists: artists in the music database
  - artist_id, name, location, latitude, longitude
- time: timestamps broken down into separate columns numerically
  - start_time, hour, day, week, month, year, weekday

## Files in Repository
- sql_queries.py: SQL queries for dropping/creating tables and inserting data
- create_tables.py: Drops and creates database and tables
- etl.py: Main ETL pipeline script that processes all data files
- etl.ipynb: Jupyter notebook for developing the ETL process
- test.ipynb: Jupyter notebook for testing database tables and data quality
- data/: Directory containing song and log JSON data files
- README.md: This file

## How to Run the Python Scripts

1. To create database and tables, run: python create_tables.py

2. To run the ETL pipeline, run: python etl.py

3. To ensure data has been loaded correctly, open and run: test.ipynb