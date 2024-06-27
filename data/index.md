---
layout: default
title: "Data Collection and Cleaning"
nav_order: 2
---

# Data Collection and Cleaning

This section contains the data related to parking availability within Gillman and Hopkins Parking Structures at UCSD.

## Data Collection
Every 10 minutes the sensors at UCSD refresh and record the number of cars inside of each parking structure. The two biggest parking structures with live sensors are the Gillman and Hopkins parking structures. The majority of students and staff park within these two parking structures posistioned conviniently around the campus.

This data was collected by calling an API using AWS Lambda. Every 30 minutes the Lambda function calls the retrieval of data and inserts two rows into a csv file located in an S3 bucket on AWS: one for Gillman and one for Hopkins parking structure.

Below are the first 5 rows of the dataframe created through this process:

| Timestamp                 | Location   |   A_Total |   A_Open |   B_Total |   B_Open |   V_Total |   V_Open |   Accessible_Total |   Accessible_Open |   SR_Total |   SR_Open | Day_of_week   |
|:--------------------------|:-----------|----------:|---------:|----------:|---------:|----------:|---------:|-------------------:|------------------:|-----------:|----------:|:--------------|
| 2024-03-30 15:32:17-07:00 | Gilman     |       388 |      371 |       122 |      102 |       198 |      190 |                 44 |                44 |          0 |         0 | Saturday      |
| 2024-03-30 15:32:17-07:00 | Hopkins    |       268 |      221 |       605 |      525 |        90 |       71 |                 25 |                25 |        189 |       149 | Saturday      |
| 2024-03-30 22:45:05-07:00 | Gilman     |       388 |      372 |       122 |      102 |       198 |      190 |                 44 |                44 |          0 |         0 | Saturday      |
| 2024-03-30 22:45:05-07:00 | Hopkins    |       268 |      221 |       605 |      526 |        90 |       71 |                 25 |                25 |        189 |       149 | Saturday      |
| 2024-03-31 07:57:28-07:00 | Gilman     |       388 |      369 |       122 |       90 |       198 |      189 |                 44 |                43 |          0 |         0 | Sunday        |

