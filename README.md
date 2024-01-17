# Music Popularity Across Platforms: United States' Spotify Charts vs. Billboard Hot 100
## Collecting Data - Group D

### Corpus Description
This corpus contains two datasets: the first includes data collected about the top 100 songs from each week of 2021 on the Spotify charts, while the second includes data collected about the top 100 songs from each week of 2021 on the Billboard Hot 100 charts.

Both sets concern data collected only from the United States.

### File Format and Content
- `.pdf` Portable document format; includes the Data Management Plan for this project
- `.csv` Comma-separated values; includes (meta)data on the songs for both the Billboard top 100 and the Spotify Top 200 charts.
- `.ipynb` Jupyter Notebook; the notebook in this repository consists of three parts:
    - Part 1: Introduction
    - Part 2: Tutorial
    - Part 3: Active Learning Exercises
   
### Target Audience
The target audiences for this corpus are record labels or even musical artists to identify popular trends in music in order to cater musical releases for maximum success - it can also be used in this way for advertisers or marketers. This corpus could also be used by data scientists or academics who study the arts and who might have research questions, hypotheses, or studies concerning musical trends, popularity, and audience or consumer interaction with music and genres.

### Intended Use
The intended usage of this corpus is to inform interested researchers, scholars, marketers, and companies. It can be used for academic purposes such as research study papers, journals, and articles, or for commercial/business purposes as it can inform companies and marketing/advertising teams about useful trends and consumer behavior(s).

The tutorial and active learning exercises in this repository are useful for people who are interested in learning about data collection and doing data analysis in Python. 

### Text Selection Criteria
The songs in the corpus were included based on their popularity rankings per month - if they were one of the top 100 most popular songs of that month, they were included. This “popularity” is defined differently by both Spotify and the Billboard Hot 100. Spotify formulates its charts through mainly algorithms that consider mostly streaming but also shares, number of listeners, including new ones, and even rates of saving songs to playlists or skipping. The Billboard Hot 100 charts are informed by several factors, including sales (physical and digital), radio airplay, digital downloads, and online streaming. Both datasets contain the necessary identifying or crucial information about the songs such as the title, the artist, and its ranking, as well as the number of weeks on the board or chart (a big indicator of overall popularity), its ranking the previous week, and its peak rank. "Date" was included to be a linking column between both datasets.

While there was extra data about Spotify’s top songs, only the top 100 were included to allow for a fair comparison to the Billboard Hot 100.


### Data Collection Process
The Billboard Hot 100 data was collected from Kaggle - a website and online community where users can share and download datasets. The owner of the dataset is [Dhruvil Dave](https://www.kaggle.com/dhruvildave). He is a graduate student from the University of Texas at Dallas. He shared this Billboard Chart dataset which includes ‘The Hot 100’ chart of songs according to Billboard’s ranking system. This dataset includes a collection of all the weekly Billboard Hot 100 charts between 04-08-1958 and 06-11-2021. Dave published the dataset on Kaggle under the license: `CC BY-NC-SA 4.0.` 

For our project’s purpose, we cleaned the data to only include the charts in 2021.

In order to collect Spotify data, web scraping from the Spotify charts website needed to be done. This website archives weekly charts from various countries. As these charts are weekly instead of monthly and include the top 200 rather than the top 100, in order to create a comprehensive dataset comparable to the Billboard Hot 100 charts, it was necessary to include the top 200 weekly charts spanning all 52 weeks of 2021. In our later cleaning and preprocessing steps, we would exclude other countries and extract the top 100 songs for a fair comparison to the Billboard charts.


### Cleaning and Preprocessing
Upon collection of the data, Python was used, particularly Jupyter Notebooks, for preprocessing. This process involved cleaning the data, organizing it efficiently, and preparing it for in-depth analysis and visualization. 

For Spotify, this included defining the columns needed from the collected data (rank, uri, artist_names, track_name, peak_rank, previous_rank, weeks_on_chart, streams, date, country, source). The next step was to combine multiple .csv files, add new columns, and extract the top 100 songs. Next was to specify the directory containing .csv files and set the country to the United States.

In order to clean and preprocess the Billboard Hot 100 data from the dataset found on Kaggle, the columns first had to be renamed in both datasets: ‘artist_names’ for ‘artist’, ‘track_name’ for ‘song’, and ‘weeks_on_chart’ for ‘weeks_on_charts’ in Spotify; ‘peak-rank’ for ‘peak_rank’ and ‘weeks-on-board’ for ‘weeks_on_charts’ for Billboard). Next was to drop columns that would not be needed: ‘uri’, ‘country’, ‘source’ (as the U.S. was previously specified in the prior preprocessing step), and  ‘previous_rank’ for Spotify, and ‘last-week’ for Billboard. Next was to change the order of the columns for uniformity between datasets as follows: song, artist, date, rank, weeks_on_charts, peak_rank, and, for Spotify only, streams.


**Columns Used in Spotify CSV:**

| Variable      | Description                                  |
| ------------- | -------------------------------------------- |
| rank  | Where the song falls in the numbered rankings    |
| uri    | Identifying string of characters for the song    |
| artist_names | The performing artist of the song                 |
| track_name      | The tile of the song |
| peak_rank    | The highest position on the charts the song has taken  |
| previous_rank  | The previous position on the charts the song has taken    |
| weeks_on_chart  | Number of weeks that the song has remained on the charts  |
| streams  | How many digital streams the song has  |
| date          | The date of the chart |
| country     | The country that the song has reached chart status in         |
| source  | The record label or company within which the song has been released  |


**Columns Used in Billboard CSV:**

| Variable      | Description                                  |
| ------------- | -------------------------------------------- |
| date          | The date of the chart |
| rank  | Where the song falls in the numbered rankings    |
| song     | The tile of the song |
| artist | The performing artist of the song                 |
| last-week  | The ranking of the song in the previous week   |
| peak-rank    | The highest position on the charts the song has taken  |
| weeks-on-board  | Number of weeks that the song has remained on the Billboard charts  |


**Contributors** 
- Shuxiang Du
- Tessa Eisen
- Linchun Hou
- Yingyue Jiang
- Maria Kutepova
- Lotte Telnekes
- Spring Wan
- Josie Wisowaty
