# Movies: Extract, Transform, Load

### Project overview
Amazing prime video is sponsoring a hackathon where teams will focus on predicting popular movies. To aid in this event, our goal is to provide a clean dataset of movies. More specifically, we create an automated pipeline that takes in new data, performs appropriate transformations, and loads the data nito existing tables. The data sources are (1) scrape of wikipedia of all movies released after 1990, rating data from MovieLens, and Kaggle metadata. The data needs to be extracted from the two sources, cleaned, and loaded into an SQL table.

### Method
1. Write an ETL function to read in the three files (wikipedia, kaggle metadata, movilens rating data)
2. clean all datasets (get rid of null values, merge information)
3. load the data into a PostgreSQL movie database

### Resources
**Data sources**: movies_metadata.csv, ratings.csv, and wikipedia-movies.json can be found in the Resources folder
**Software**: Python 3.8.5, Conda 4.10.1, Jupyter notebook 6.1.4, pgADMIN 4

## Results
1. def extract_transform_load() reads in the movies_metadata.csv, ratings.csv, and wikipedia-movies.json files and creates pandas dataframes. 
2. dataframes are cleaned by filtering out TV shows, formatting units for budget and box office columns, parsing the release date, dropping duplicate values and merging on IMDB ID. See the ETL_clean_kaggle_data.ipynb file for a detailed perspective on how data was cleaned per column.
3. Data was then loaded into a postgreSQL movie database using pgADMIN. Fig. 1 and 2 are images of the queries to count the number of rows in the movies (Fig. 1) and ratings (Fig. 2) tables respectively. 

**Fig. 1** Movies table count row query

<img width="429" alt="movies_query" src="https://user-images.githubusercontent.com/45336910/124537822-9eb8e280-dde8-11eb-9592-566d860befa5.png">

**Fig. 2** Ratings table count row query

<img width="443" alt="ratings_query" src="https://user-images.githubusercontent.com/45336910/124537885-b8f2c080-dde8-11eb-8c0a-e8482a7f5f7c.png">
