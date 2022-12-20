## Introduction
In this project, I will try to analyze video game sales dataset from [kaggle](https://www.kaggle.com/datasets/gregorut/videogamesales) and using BigQuery.

## About Dataset
This dataset contains a list of video games with sales greater than 100,000 copies.  
Fields include:
*	Rank - Ranking of overall sales
*	Name - The games name
*	Platform - Platform of the games release (i.e. PC,PS4, etc.)
*	Year - Year of the game's release
*	Genre - Genre of the game
*	Publisher - Publisher of the game
*	NA_Sales - Sales in North America (in millions)
*	EU_Sales - Sales in Europe (in millions)
*	JP_Sales - Sales in Japan (in millions)
*	Other_Sales - Sales in the rest of the world (in millions)
*	Global_Sales - Total worldwide sales.

## Analyzing the data
1. Which platform is the most popular?  
```sql
SELECT Platform, COUNT(Platform) as Numb_Platform FROM `vgsales.video_game_sales` GROUP BY Platform ORDER BY Numb_Platform DESC LIMIT 5;
```
2. Which published most of the games?
```sql
SELECT Publisher, COUNT(Publisher) as Count_Pub FROM `vgsales.video_game_sales` GROUP BY Publisher ORDER BY Count_Pub DESC LIMIT 5;
```
3. Which games genre is the most popular?
```sql
SELECT Genre, COUNT(Genre) as Count_Genre FROM `vgsales.video_game_sales` GROUP BY Genre ORDER BY Count_Genre DESC LIMIT 5;
```
4. Which the most selling video game on 2012 based on global sales?
```sql
SELECT Name, Global_Sales FROM `vgsales.video_game_sales` WHERE Year = '2012' ORDER BY Global_Sales DESC LIMIT 5;
```
5. 5 games with lowest global sales
```sql
SELECT Name, Global_Sales FROM `vgsales.video_game_sales` ORDER BY Global_Sales ASC LIMIT 5;
```
6. 5 most selling game in europe on 2010-2012
```sql
SELECT Name, Year, EU_Sales as Europe_Sales FROM `vgsales.video_game_sales` WHERE Year BETWEEN '2010' AND '2012' ORDER BY Europe_Sales DESC LIMIT 5;
```
