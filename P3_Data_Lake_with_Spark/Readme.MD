## Introduction

The purpose of this database is to enable Sparkify to answer business questions it may have of its users, the types of songs they listen to and the artists of those songs using the data that it has in logs and files. The database provides a consistent and reliable source to store this data.

This source of data will be useful in helping Sparkify reach some of its analytical goals, for example, finding out songs that have highest popularity or times of the day which is high in traffic.

## Database Design and ETL Pipeline
1. For the schema design, the STAR schema is used as it simplifies queries and provides fast aggregations of data.
<img width="354" alt="image" src="https://user-images.githubusercontent.com/34394130/114564993-27eccd00-9c71-11eb-98da-c4170debe7db.png">

2. For the ETL pipeline,
    
  - Read data from S3
    
    -   Song data:  `s3://udacity-dend/song_data`
    -   Log data:  `s3://udacity-dend/log_data`
    
    The script reads song_data and load_data from S3.
    
  - Process data using spark
    
    Transforms them to create five different tables listed below : 
    #### Fact Table
	 **songplays**  - records in log data associated with song plays i.e. records with page  `NextSong`
    -   _songplay_id, start_time, user_id, level, song_id, artist_id, session_id, location, user_agent_

	#### Dimension Tables
	 **users**  - users in the app
		Fields -   _user_id, first_name, last_name, gender, level_
		
	 **songs**  - songs in music database
    Fields - _song_id, title, artist_id, year, duration_
    
	**artists**  - artists in music database
    Fields -   _artist_id, name, location, lattitude, longitude_
    
	  **time**  - timestamps of records in  **songplays**  broken down into specific units
    Fields -   _start_time, hour, day, week, month, year, weekday_
    
  - Load it back to S3
    
    Writes them to partitioned parquet files in table directories on S3.

## How to Run
Run etl.py to read from the song and logs json files, denormalize the data into fact and dimension tables and gives the output of these tables in S3 in the form of parquet files.
