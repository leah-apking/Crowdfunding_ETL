### Crowdfunding_ETL

## Project 2: The ETL Mini Poject

For this assignment we decided to take more of a study group approach, each completing and turning in our own assignment while assisting and supporting each other along the way. This project involved using Python and Pandas to extract, transform, and clean data files, and then upload those files to a Postgres database.

### Extract, Transform

Much of this project focused on cleaning provided excel files in Jupyter notebooks. The first task was to split the category/subcategory column assign each category and subcategory an ID an create two separate DataFrames containing this information leaving only the corresponding IDs on the original DataFrame.To do this we used the split function, created a list with the unique (sub)categories, created unique IDs with list comprehension, and created two DataFrames connecting the IDs to the corresponding categories. Later the merge function was used to replace the categories with their IDs before dropping the redundant columns. After renaming columns and assigning the correct data types we used the datetime function to convert the provided UTC times into common date formatting. Each DataFrame was then exported to a CSV file to eventually be used to create the SQL database.

The contacts file was not formatted in a way that allowed us to convert the data directly into columns and rows, instead each row contained a individuals’ information in a single string of text. Two options were given for extracting and transforming the data, Python dictionary methods or the use of regular expressions. I chose to use a series of Regex extractions to pull each bit of information into its own column. This cleaned DataFrame was then exported to another CSV file.

### Load

The final task for this mini project was to create a SQL database with the files we had cleaned in part 1. This involved creating an ERD sketch in QuickDBD to determine the links between tables, data types, and to specify primary and foreign keys. The information from the ERD sketch allowed us to create a table schema for each CSV file that needed to be included in the database. Finally, we used Postgres to create our database, run our schema, and import our files.
