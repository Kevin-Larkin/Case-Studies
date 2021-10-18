# Cyclistic Case Study

This is a case study I completed as part of the Google Data Analytics Certificate. The analysis was done for a fictional ride-sharing company called Cyclistic, which was based on data from Divvy bikes, a ride-share company in Chicago, USA. The purpose of this analysis was to discover how annual members and casual riders use Cyclistic bikes differently in order to better inform a marketing strategy aimed at converting more casual riders into annual members. The main tools used for this analysis were Excel, Postgres, Tableau, and PowerPoint. Below I have listed how I approached each of the six steps of the data analysis process while working on this project.

Step 1: Ask

The business task is "How do annual members and casual riders use Cyclistic bikes differently?"
The key stakeholders are the Cyclistic executive team, who decides whether the recommended marketing program is approved, Lily Moreno, the director of marketing and my manager, and the Cyclistic marketing analytics team, a team of data analysts who are responsible for collecting, analyzing, and reporting data that helps guide Cyclistic marketing strategy.

Step 2: Prepare

Datasets Used: (202009-divvy-tripdata.zip – 202108-divvy-tripdata.zip) https://divvy-tripdata.s3.amazonaws.com/index.html
Data Liscense Agreement: Motivate International Inc. (“Motivate”) operates the City of Chicago’s (“City”) Divvy bicycle sharing service. Motivate and the City are committed to supporting bicycling as an alternative transportation option. As part of that commitment, the City permits Motivate to make certain Divvy system data owned by the City (“Data”) available to the public, subject to the terms and conditions of this License Agreement (“Agreement”). https://www.divvybikes.com/data-license-agreement
Bias and Credibility: These datasets are monthly collections of all rides that took place using Divvy bikes in Chicago. The datasets used for this analysis were the September 2020 - August 2021 datasets. All together, there were 4,195,359 total trips over all 12 months. 
Reliability- Unless the company collecting this data had a preference towards a specific type of rider or bike type and excluded data that didn't meet those preferences, I don't see a way selection bias could be present. Excluding trips would also hinder this analysis and give less reliable results, thus a misinformed marketing plan which would waste advertising money. Thus, it wouldn't beneficial for Divvy to exclude data from these sets. 
Originality- The datasets were collected straight from Divvy, which is the company whose data were analyzing.
Comprehensive- Many of the datasets are missing information like start and end station names and IDs, but this will be addressed in the cleaning process.
Current- I'm using the past 12 months worth of data, so yes it's current data.
Cited- Considering it's a first-party source, the creator of the data is the company Motivate International Inc., which operates the city's Divvy service.

Step 3: Process

The tools used for this analysis were Excel, Postgres, and Tableau. Due to the size of the datasets, Excel couldn't be used for much cleaning or analyzing, and was only used to add the 'day_of_week' row into each dataset and check for duplicates. Then, all the datasets were imported into SQL where most of the cleaning and analyzing took place. After all the tables were imported into SQL, I added the 'ride_length' column to each table. After reviewing the data and doing some basic queries to get familiar with it, I decided what steps would be needed to clean it further.
First, I removed all instances that had a ride length that was either negative (meaning the start time came after the end time) or '00:00:00'
Then, I removed all rows where the start or end station names were missing. I brainstormed ways to fill in the missing start and end station names, as there were quite a large amount missing. I first considered using the coordinates provided in each trip to map station names to specific coordinates. However, the coordinates for the same station names were not always exactly the same, making it impossible (at least to my knowledge) to look up all instances at a specific station searching by coordinates. I considered rounding coordinates, but could not find a reliable and consistent way of doing this without messing up the precision of the coordinates. I then considered using the station IDs for the same purpose, but ran into a similar issue. Station IDs were not the same even for the same station, so they couldn’t be used either.

Step 4: Analyze

Before I started analyzing, I reviewed the objective of this analysis and thought about specific questions I could answer using the data to answer the bigger objective question. I also grouped some data together to create bigger tables to answer specific questions. For example, I combined all 12 months worth of data into one table to analyze trends over the entire year, and certain months together to analyze trends over the various seasons.
The first question I asked was 'how many rides are from casual riders vs. members?' I used SQL queries to get counts for both overall and by each seasonI decided what steps would be needed to clean it further.
First, I removed all instances that had a ride length that was either negative (meaning the start time came after the end time) or '00:00:00'
Then, I removed I brainstormed ways to fill in the missing start and end station names, as there were quite a large amount missing. I first considered using the coordinates provided in each trip to map station names to specific coordinates. However, the coordinates for the same station names were not always exactly the same, making it impossible (at least to my knowledge) to look up all instances at a specific station searching by coordinates. I considered rounding coordinates, but could not find a reliable and consistent way of doing this without messing up the precision of the coordinates. I then considered using the station IDs for the same purpose, but ran into a similar issue. Station IDs were not the same even for the same station, so they couldn’t be used either.
Then, I removed all rows where the start or end station names were missing. I brainstormed ways to fill in the missing start and end station names, as there were quite a large amount missing. I first considered using the coordinates provided in each trip to map station names to specific coordinates. However, the coordinates for the same station names were not always exactly the same, making it impossible (at least to my knowledge) to look up all instances at a specific station searching by coordinates. I considered rounding coordinates, but could not find a reliable and consistent way of doing this without messing up the precision of the coordinates. I then considered using the station IDs for the same purpose, but ran into a similar issue. Station IDs were not the same even for the same station, so they couldn’t be used either.

Step 4: Analyze

Before I started analyzing, I reviewed the objective of this analysis and thought about specific questions I could answer using the data to answer the bigger objective question. I also grouped together tables into bigger ones to perform specific analyses on them. For example, I combined all 12 months worth of data into one table to analyze trends over the entire year. I also combined certain months into separate tables to analyze trends over all four months. All questions were first answered and explored in SQL, then again in Tableau while creating the visulizations. SQL code and PowerPoint can be found here on my GitHub.
Q1: How many rides are from casual riders vs. members? 
Q2: What rideable (or bike_ type is most popular?
Q3: How many rides took place on each day of the week?
Q4: What was the average ride length?
Q5: What routes are the most popular?

Steps 5 and 6: Share and Act
Top 3 recommendations based on analysis:
1: Increase advertising efforts in warmer seasons and at stations casual riders use most often, such as Streeter Dr & Grand Ave, Lake Shore Dr & Monroe St, and Millennium Park.
2: Target casual riders that use bikes in similar ways to members, such as casual riders who ride on weekdays.
3: Provide rewards incentives for becoming a member the more you ride, since casual riders ride for much longer durations.
