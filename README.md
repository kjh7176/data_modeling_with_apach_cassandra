# Data Modeling with Apache Cassandra
This is the second project of Udacity's **Data Engineering Nanodegree**:mortar_board:.  
The purpose is to build an **ETL pipeline** transferring data from `CSV` to `Apache Cassandra database` using `Python` and `CQL`

## Background
A startup called :musical_note:*Sparkify* wants to analyze the data they've been collecting on songs and user activity on their new music streaming app.  
The analytics team is particularly interested in understanding what songs users are listening to.  
Currently, there is no easy way to query the data to generate the results, since the data reside in a directory of CSV files on user activity on the app.

## File Description
- `Project_1B_ Project_Template.ipynb` reads and a single file from `event_data/song_data` and collect all data into the new csv file named 
- `event_datafile_new.csv` is created after execution of the above file. This has all data from `event_data/song_data`.

## ETL Pipeline
- Database Schema Diagram  
  `song_play`  
  | column | datatype | primary key |
  |:---: | :---:| :---:|
  |session_id| int|partition key|
  |item_in_session| int|clustering key|
  |artist| text||
  |song_title| text||
  |song_length| float||
  
  `user_playhistory`  
  | column | datatype | primary key |
  |:---: | :---:| :---:|
  |user_id| int|partition key 1|
  |session_id| int|partition key 2|
  |item_in_session| int|clustering key|
  |artist| text||
  |song_title| text||
  |first_name| text||
  |last_name| text||
  
  `song_userlist`  
  | column | datatype | primary key |
  |:---: | :---:| :---:|
  |song_title| text|partition key|
  |artist| text|clustering key|
  |first_name| text||
  |last_name| text||

## Example
> Query  
```
SELECT artist, song_title, song_length FROM music_history 
WHERE session_id = 338 and item_in_session = 4
```
> Result  

![music_history](/images/music_history.PNG)
   
> Query  
```
SELECT artist, song_title, first_name, last_name FROM user_playhistory 
WHERE user_id = 10 and session_id = 182
```
> Result  

![music_history2](/images/music_history2.PNG)
   
> Query  
```
SELECT first_name, last_name FROM song_userlist 
WHERE song_title = 'All Hands Against His Own'
```
> Result  

![music_history3](/images/music_history3.PNG)
