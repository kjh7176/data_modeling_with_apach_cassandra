# Data Modeling with Apache Cassandra
This is the second project of Udacity's **Data Engineering Nanodegree**:mortar_board:.  
The purpose is to build an **ETL pipeline** transferring data from `CSV` to `Apache Cassandra database` using `Python` and `CQL`

## Background
A startup called :musical_note:*Sparkify* wants to analyze the data they've been collecting on songs and user activity on their new music streaming app.  
The analytics team is particularly interested in understanding what songs users are listening to.  
Currently, there is no easy way to query the data to generate the results, since the data reside in a directory of CSV files on user activity on the app.


## ETL Pipeline
- Database Schema Diagram  
  `music_history`
  | column | datatype |
  |:--- | :---|

## Example
> Query  
```
SELECT * FROM songplays LIMIT 5;
```
> Result  

![songplays](/images/songplays.PNG)
   
> Query  
```
SELECT * FROM users LIMIT 5;
```
> Result  

![users](/images/users.PNG)
   
> Query  
```
SELECT * FROM songs LIMIT 5;
```
> Result  

![songs](/images/songs.PNG)

> Query  
```
SELECT * FROM artists LIMIT 5;
```
> Result  

![artists](/images/artists.PNG)
  
> Query  
```
SELECT * FROM time LIMIT 5;
```
> Result  

![time](/images/time.PNG)