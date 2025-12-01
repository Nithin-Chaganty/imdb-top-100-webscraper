# IMDb Top 100 Web Scraper

This project scrapes the IMDb Top 250 page and collects data for the top 100 ranked movies. It extracts each movie's title, IMDb URL, rating, rating count, content rating, and duration, then saves the results as a CSV file for analysis.

This was a simple project where I learned how to web scrape data from the internet. In the future I can reuse this approach to collect other datasets for data science projects.

## Purpose

The purpose of this project is to practice basic web scraping, data cleaning, and exporting a structured dataset. It shows how to go from a public website to a reusable CSV that can be used later for analysis, visualization, or recommendation models.

## Dataset

**Dataset Title:** IMDb Top 100 Movies  

This dataset was created by scraping the IMDb Top 250 list and collecting details for the top 100 ranked movies. The data includes titles, ratings, content warnings, and other metadata available on IMDb.

**Variables**

- `Title`  
  Name of the movie  

- `URL`  
  Direct link to the movie’s IMDb page  

- `IMDb Rating`  
  Average viewer rating out of 10  

- `Rating Count`  
  Number of votes the movie has received  

- `Content Rating`  
  Age based content classification (for example PG, PG 13, R)  

- `Duration`  
  Length of the movie formatted in hours and minutes  

**Source**  
IMDb Top 250: https://www.imdb.com/chart/top/  

**Date Created**  
05 16 2025  

## Methods

Tools used:

- Python  
- `requests` to download the HTML page  
- `BeautifulSoup` to parse the HTML  
- `json` to load the structured data embedded in the page  
- `pandas` to build and export the dataset  

Steps:

1. Send a GET request to the IMDb Top 250 page with a header that mimics a browser  
2. Locate the `<script>` tag that contains JSON with the movie list  
3. Load the JSON and slice the first 100 movies  
4. For each movie, extract:
   - Title  
   - URL  
   - IMDb rating and rating count  
   - Content rating  
   - Duration in ISO format, converted to `Xh Ymin`  

5. Store all records in a pandas DataFrame  
6. Export the data to `imdb_top_100.csv`  
7. Save a metadata text file that documents the dataset  

## Visualizations

To explore the dataset, I created a boxplot of IMDb rank by content rating:

- Added a `Rank` column from 1 to 100  
- Filtered to common content ratings such as G, PG, PG 13, R, and Not Rated  
- Plotted a boxplot of `Rank` by `Content Rating` to see how highly rated movies are distributed across age ratings  

This is a starting point for more detailed analysis of movie ratings and content categories.

## Files

- `Webscraping.ipynb`  
  Jupyter notebook with all scraping and analysis code  

- `README.md`  
  Project overview and documentation  
