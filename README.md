# Movies-ETL

# Module 8

Background
Amazing Prime loves the dataset and wants to keep it updated on a daily basis. Britta needs your help to create an automated pipeline that takes in new data, performs the appropriate transformations, and loads the data into existing tables. You’ll need to refactor the code from this module to create one function that takes in the three files—Wikipedia data, Kaggle metadata, and the MovieLens rating data—and performs the ETL process by adding the data to a PostgreSQL database.

What You're Creating
This new assignment consists of four technical analysis deliverables. You will submit the following:

Deliverable 1: Write an ETL Function to Read Three Data Files
https://github.com/Dybondzy/Movies-ETL/blob/main/ETL_function_test.ipynb

Deliverable 2: Extract and Transform the Wikipedia Data
https://github.com/Dybondzy/Movies-ETL/blob/main/ETL_clean_wiki_movies.ipynb

Deliverable 3: Extract and Transform the Kaggle data
https://github.com/Dybondzy/Movies-ETL/blob/main/ETL_clean_kaggle_data.ipynb

Deliverable 4: Create the Movie Database
https://github.com/Dybondzy/Movies-ETL/blob/main/ETL_create_database.ipynb

Deliverable 1: Write an ETL Function to Read Three Data Files (25 points)
Deliverable 1 Instructions
Using your knowledge of Python, Pandas, the ETL process, and code refactoring, write a function that reads in the three data files and creates three separate DataFrames.

Download the ETL_Deliverable1_starter_code.ipynb file, add it to your Movies-ETL GitHub folder, and rename the file ETL_function_test.ipynb. Follow the instructions below to refactor the code from this module as indicated by the numbered comments in the starter code file.

In Step 1, create a function to read in the three files and give it a name.

In Step 2, read in the Kaggle metadata and MovieLens ratings CSV files as Pandas DataFrames.
In Step 3, open the Wikipedia JSON file and use the json.load() function to convert the JSON data to raw data.
In Step 4, read in the raw Wikipedia movie data as a Pandas DataFrame.
In Step 5, use the code provided to return the three DataFrames.
In Step 6, use the variables provided to create a path to the Wikipedia data, the Kaggle metadata, and the MovieLens rating data files.
In Step 7, set the three variables in Step 6 equal to the function created in Step 1.
In Step 8, set the DataFrames from the return statement equal to the file names in Step 6. In this step, you are reassigning the variables created in Step 6 to the variables in the return statement.
In Steps 9-11, check that all three files are converted to a DataFrame. See the images below for confirmation:
The wiki_movies_df DataFrame

The kaggle_metadata DataFrame

The ratings DataFrame

After you confirm that all three DataFrames are correct, save the ETL_function_test.ipynb file in your Movies-ETL GitHub folder.
Deliverable 1 Requirements
You will earn a perfect score for Deliverable 1 by completing all requirements below:

An ETL function is written to read in the three data files. (10 pt)
The function converts the Wikipedia JSON file to a Pandas DataFrame, and the DataFrame is displayed in the ETL_function_test.ipynb file. (5 pt)
​The function converts the Kaggle metadata file to a Pandas DataFrame, and the DataFrame is displayed in the ETL_function_test.ipynb file. (5 pt)
​The function converts the MovieLens ratings data file to a Pandas DataFrame, and the DataFrame is displayed in the ETL_function_test.ipynb file. (5 pt)
Deliverable 2: Extract and Transform the Wikipedia Data (30 points)
Deliverable 2 Instructions
Using your knowledge of Python, Pandas, the ETL process, and code refactoring, extract and transform the Wikipedia data so you can merge it with the Kaggle metadata. While extracting the IMDb IDs using a regular expression string and dropping duplicates, use a try-except block to catch errors.

Download the ETL_Deliverable2_starter_code.ipynb file, add it to your Movies-ETL GitHub folder, and rename the file ETL_clean_wiki_movies.ipynb. Follow the instructions below to refactor the code from this module as indicated by the numbered comments in the starter code file.

In Step 1, add the code from this module for the clean movie function that takes in the argument "movie".
In Step 2, add the function you created in Deliverable 1 that reads in the three data files.
In Step 3, inside the function you created in Deliverable 1, remove the code that creates the wiki_movies_df DataFrame from the wiki_movies_raw file, then write a list comprehension that filters out TV shows from the wiki_movies_raw file.
In Step 4, write a list comprehension to iterate through the cleaned wiki movies list that you created in Step 3.
In Step 5, read in the cleaned movies list from Step 4 as a DataFrame.
In Step 6, write a try-except block that will catch errors while extracting the IMDb IDs with a regular expression string and dropping any imdb_id duplicates. If there is an error, capture and print the exception.
In Step 7, write a list comprehension to keep the columns that have non-null values from the DataFrame created in Step 5, then create a wiki_movies_df DataFrame from the list.
In Step 8, create a variable that will hold all the non-null values from the "Box office" column.
In Step 9, convert the box office data created in Step 8 to string values using the lambda and join functions.
In Step 10, write a regular expression to match the six elements of form_one of the box office data.
In Step 11, write a regular expression to match the three elements of form_two of the box office data.
In Step 12, add the parse_dollars() function.
In Step 13, add the code that cleans the box office column in the wiki_movies_df DataFrame using the form_one and form_two lists created in Steps 10 and 11, respectively.
In Step 14, add code that cleans the budget column in the wiki_movies_df DataFrame.
In Step 15, add code that cleans the release date column in the wiki_movies_df DataFrame.
In Step 16, add code that cleans the running time column in the wiki_movies_df DataFrame.
In Step 17, use the variables provided to create a path to the Wikipedia data, the Kaggle metadata, and the MovieLens rating data files.
In Step 18, set the three variables in Step 17 equal to the function created in Deliverable 1.
In Step 19, set the wiki_movies_df equal to the wiki_file variable.
In Step 20, check that your wiki_movies_df DataFrame looks like this image:

In Step 21, add the columns from wiki_movies_df DataFrame to a list, and confirm that they are the same as this image:

After you confirm that the wiki_movies_df DataFrame is correct, save the ETL_clean_wiki_movies.ipynb file in your Movies-ETL GitHub folder.
Deliverable 2 Requirements
You will earn a perfect score for Deliverable 2 by completing all requirements below:

The TV shows are filtered out, and the wiki_movies_df DataFrame is created. (3 pt)
A try-except block is used to catch errors while extracting the IMDb IDs with a regular expression and dropping duplicate IDs. (5 pt)
The extraction and transformation of the Wikipedia data in the ETL function does the following:
A list comprehension is used to keep columns with non-null values. (3 pt)
The non-null box office data is converted to string values using the lambda and join functions. (3 pt)
A regular expression is used to match the six elements of "form_one" of the box office data. (2 pt)
A regular expression is used to match the three elements of "form_two" of the box office data. (2 pt)
The following columns are cleaned in the Wikipedia DataFrame: (8 pt)
The box office column
The budget column
The release date column
The running time column
​The cleaned Wikipedia data is converted to a Pandas DataFrame, and the DataFrame is displayed in the ETL_clean_wiki_movies.ipynb file. (4 pt)
Deliverable 3: Extract and Transform the Kaggle Data (30 points)
Deliverable 3 Instructions
Using your knowledge of Python, Pandas, the ETL process, and code refactoring, extract and transform the Kaggle metadata and MovieLens rating data, then convert the transformed data into separate DataFrames. Then, you’ll merge the Kaggle metadata DataFrame with the Wikipedia movies DataFrame to create the movies_df DataFrame. Finally, you’ll merge the MovieLens rating data DataFrame with the movies_df DataFrame to create the movies_with_ratings_df.

Download the ETL_Deliverable3_starter_code.ipynb file, add it to your Movies-ETL GitHub folder, and rename the file ETL_clean_kaggle_data.ipynb. Follow the instructions below to refactor the code from this module as indicated by the numbered comments in the starter code file.

In Step 1, add the function you created in Deliverable 1 that reads in the three data files and creates the kaggle_metadata and ratings DataFrames.
Before Step 2, add all the code you wrote for Deliverable 2.
In Step 2, below the code that cleans the running time column in the wiki_movies_df DataFrame from Deliverable 2, add the code that cleans the Kaggle metadata.
In Step 3, merge the wiki_movies_df DataFrame and the kaggle_metadata DataFrames, then name the new DataFrame, movies_df.
In Step 4, drop unnecessary columns from the movies_df DataFrame.
In Step 5, add the fill_missing_kaggle_data() function that fills in the missing Kaggle data on the movies_df DataFrame.
In Step 6, call the fill_missing_kaggle_data() function with the movies_df DataFrame and the Kaggle and Wikipedia columns to be cleaned as the arguments.
In Step 7, filter the movies_df DataFrame to keep the necessary columns.
In Step 8, rename the columns in the movies_df DataFrame.
In Step 9, transform and merge the ratings DataFrame with the movies_df DataFrame, name the new DataFrame movies_with_ratings_df, then clean the movies_with_ratings_df DataFrame.
In Step 10, use the variables provided to create a path to the Wikipedia data, the Kaggle metadata, and the MovieLens rating data files.
In Step 11, set the three variables from Step 17 of Deliverable 2 equal to the function created in Deliverable 1.
In Step 12, set the DataFrames from the return statement after Step 9 equal to the file names in Step 11.
In Step 13, check that your wiki_movies_df DataFrame is the same as in Deliverable 2.
In Step 14, check that your movies_with_ratings_df DataFrame looks like this image:

In Step 15, check that your movies_df DataFrame looks like this image:

After you confirm that all three DataFrames are correct, save the ETL_clean_kaggle_data.ipynb file in your Movies-ETL GitHub folder.
Deliverable 3 Requirements
You will earn a perfect score for Deliverable 3 by completing all requirements below:

The extraction and transformation of the Kaggle metadata using the ETL function does the following:
The Kaggle metadata is cleaned. (4 pt)
The Wikipedia and Kaggle DataFrames are merged. (3 pt)
The following is performed on the merged Wikipedia and Kaggle DataFrames to create the movies_df: (8 pt)
Unnecessary columns are dropped.
A function is used to fill in the missing Kaggle data.
The movies_df DataFrame is filtered to keep specific columns.
The movies_df DataFrame columns are renamed.
The extraction and transformation of the MovieLens ratings data using the ETL function does the following:
The ratings counts are cleaned. (3 pt)
The movies_df DataFrame is merged with the cleaned ratings DataFrame to create the movies_with_ratings_df DataFrame. (4 pt)
The empty values in the movies_with_ratings_df DataFrame are filled with “0”. (3 pt)
The movies_with_ratings_df and the movies_df DataFrames are displayed in the ETL_clean_kaggle_data.ipynb file. (5 pt)
Deliverable 4: Create the Movie Database (15 points)
Deliverable 4 Instructions
Use your knowledge of Python, Pandas, the ETL process, code refactoring, and PostgreSQL to add the movies_df DataFrame and MovieLens rating CSV data to a SQL database.

Make a copy of the ETL_clean_kaggle_data.ipynb file in the Movies-ETL GitHub, and rename the file ETL_create_database.ipynb. Follow the instructions below to add the movies_df DataFrame and MovieLens rating CSV data to a SQL database.

In the first cell, uncomment the # from config import db_password so this code is working.
Remove the return statement, return wiki_movies_df, movies_with_ratings_df, movies_df.
After Step 9, Transform and merge the ratings DataFrame, add the code to create the connection to the PostgreSQL database, then add the movies_df DataFrame to a SQL database.
Hint: Use 'replace' for the if_exists parameter so that the movies_df DataFrame data won't be added to the table again.

Before reading in the MovieLens rating CSV data, drop the ratings table in pgAdmin.
Add the code that prints out the elapsed time to import each row.
Refactor Step 11 of Deliverable 3 so that you pass in the variables for the files created in Step 10 of Deliverable 3 in the function created in Deliverable 1.
Run the program.
After the program has finished, run a query on the PostgreSQL database that retreives the number of rows for the movies and ratings tables.
After you confirm that the movies table has 6,052 rows and the ratings table has 26,024,289 rows, take a screenshot of each query and the output, then save them as movies_query.png and ratings_query.png, respectively.
Save the ETL_create_database.ipynb file in your Movies-ETL GitHub folder.
Save the movies_query.png and ratings_query.png files in the Resources folder.
Deliverable 4 Requirements
You will earn a perfect score for Deliverable 4 by completing all requirements below:

The data from the movies_df DataFrame replaces the current data in the movies table in the SQL database, as determined by the movies_query.png. (5 pt)
The data from the MovieLens rating CSV file is added to the ratings table in the SQL database, as determined by the ratings_query.png. (5 pt)
The elapsed time to add the data to the database is displayed in the ETL_create_database.ipynb file. (5 pt)
Submission
Once you’re ready to submit, make sure to check your work against the rubric to ensure you are meeting the requirements for this Challenge one final time. It’s easy to overlook items when you’re in the zone!

As a reminder, the deliverables for this Challenge are as follows:

Deliverable 1: Write an ETL function to read three data files
Deliverable 2: Extract and Transform the Wikipedia Data
Deliverable 3: Extract and Transform the Kaggle Data
Deliverable 4: Create the Movie Database

Upload the following to your Movies-ETL GitHub repository:

The ETL_function_test.ipynb file
https://github.com/Dybondzy/Movies-ETL/blob/main/ETL_function_test.ipynb

The ETL_clean_wiki_movies.ipynb file
https://github.com/Dybondzy/Movies-ETL/blob/main/ETL_clean_wiki_movies.ipynb

The ETL_clean_kaggle_data.ipynb file
https://github.com/Dybondzy/Movies-ETL/blob/main/ETL_clean_kaggle_data.ipynb

The ETL_create_database.ipynb file
https://github.com/Dybondzy/Movies-ETL/blob/main/ETL_create_database.ipynb

The Resources folder with the wikipedia.movies.json, movies_metadata.csv, ratings.csv, movies_query.png, and ratings_query.png files
A README.md that describes the purpose of the repository. Although there is no graded written analysis for this Challenge, it is encouraged and good practice to add a brief description of your project.
The following files were too big for GitHub, so couldn't upload
wikipedia.movies.json, movies_metadata.csv, ratings.csv

To submit your Challenge assignment in Canvas, click Submit, then provide the URL of your Movies-ETL GitHub repository for grading.

