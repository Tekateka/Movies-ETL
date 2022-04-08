# Movies-ETL

## Project Overview
Amazing Prime loves the dataset and wants to keep it updated on a daily basis. They would like to create an automated 
pipeline that takes in new data, performs the appropriate transformations, and loads the data into existing tables.

## Purpose: - 
To write ETL function to read Wikipedia data, Kaggle metadata, and the MovieLens rating data and to create three separate DataFrames.
To extract and transform the Wikipedia and Kaggle data
To create the movie database; PostgresSQL movie Database

## Resources: - 
wikipedia-movies.json, movies_metadata.csv and ratings.csv

## Results: - (please refer to the attached files for details)
Deliverable 1:  ETL Function was written to read three data files
Deliverable 2 and 3: Wikipedia and Kaggle data were extracted and transformed 
Deliverable 4: Movie database was created  
Load the data to a PostgregSQL movie database

  db_string = f"postgresql://postgres:{db_password}@localhost:5432/movie_data"
    # create database engine
    engine = create_engine(db_string)
    movies_df.to_sql(name='movies', con=engine, if_exists='replace')
    rows_imported = 0
get the start_time from time.time()
    start_time = time.time()
    for data in pd.read_csv(f'ratings.csv', chunksize=1000000):
        print(f'importing rows {rows_imported} to {rows_imported + len(data)}...', end='')
        data.to_sql(name='ratings', con=engine, if_exists='append')
        rows_imported += len(data)
    # add elapsed time to final print out
        print(f'Done. {time.time() - start_time} total seconds elapsed')

![Map](movies_query.PNG)
![Map](ratings_query.PNG)