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
SELECT Platform, COUNT(Platform) as Number_Platform FROM `vgsales.video_game_sales` GROUP BY Platform ORDER BY Number_Platform DESC LIMIT 3;
```
