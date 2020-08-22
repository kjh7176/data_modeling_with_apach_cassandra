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
  `music_history`  
  | column | datatype | primary key |
  |:---: | :---:| :---:|
  |artist| text||
  |first_name| text||
  |gender| text||
  |item_in_session| int|clustering key|
  |last_name| text||
  |song_length| float||
  |level| text||
  |location| text||
  |session_id| int|partition key|
  |song_title| text||
  |user_id| int||
  
  `music_history2`  
  | column | datatype | primary key |
  |:---: | :---:| :---:|
  |artist| text||
  |first_name| text||
  |gender| text||
  |item_in_session| int|clustering key 2|
  |last_name| text||
  |song_length| float||
  |level| text||
  |location| text||
  |session_id| int|clustering key 1|
  |song_title| text||
  |user_id| int|partition key|
  
  `music_history3`  
  | column | datatype | primary key |
  |:---: | :---:| :---:|
  |artist| text||
  |first_name| text||
  |gender| text||
  |item_in_session| int||
  |last_name| text||
  |song_length| float||
  |level| text||
  |location| text||
  |session_id| int||
  |song_title| text|partition key|
  |user_id| int||

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
SELECT artist, song_title, first_name, last_name FROM music_history2 
WHERE user_id = 10 and session_id = 182
```
> Result  

![music_history2](/images/music_history2.PNG)
   
> Query  
```
SELECT first_name, last_name FROM music_history3 
WHERE song_title = 'All Hands Against His Own'
```
> Result  

![music_history3](/images/music_history3.PNG)