# music-streaming-sql-analysis
SQL project analyzing music streaming data: cleaning, transformation, and insights
# 🎧 Music Streaming Data Analysis (SQL Project)

## Overview
This project explores music streaming data to uncover insights about artist performance, platform monetization, and audience distribution.

The dataset was cleaned and analyzed using SQL, focusing on real-world data issues such as inconsistent formats and missing values.

## Data Cleaning
### Data Cleaning Process

The dataset contained several inconsistencies which were resolved:

- Identified and handled missing values in the `streams` column
- Converted empty strings into NULL values
- Standardized categorical data (platforms and genres)
- Fixed inconsistent date formats into a unified DATE format
- Created a separate cleaned table to preserve the raw dataset

These steps ensured the dataset was reliable for analysis.

### Key SQL Queries

-- Top Artists by Streams
SELECT artist, SUM(streams) AS total_streams
FROM clean_music_streaming
GROUP BY artist
ORDER BY total_streams DESC;

-- Average Revenue by Platform
SELECT platform, AVG(revenue_usd) AS avg_revenue
FROM clean_music_streaming
GROUP BY platform
ORDER BY avg_revenue DESC;

-- Streams by Country
SELECT country, SUM(streams) AS total_streams
FROM clean_music_streaming
GROUP BY country
ORDER BY total_streams DESC;

### Key Insights

- The top 3 artists have very similar total streams, indicating strong competition in streaming performance
- Apple Music generates the highest average revenue, suggesting stronger monetization compared to other platforms
- Nigeria has the highest number of streams, highlighting a strong and growing listener base
- Some platforms generate high streams but lower revenue, indicating differences in business models

### Conclusion

This project demonstrates how SQL can be used to clean messy datasets and extract meaningful insights. It highlights the importance of data cleaning and shows how data can reveal patterns in music consumption and platform performance.

