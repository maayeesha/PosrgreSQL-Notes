# PosrgreSQL-Notes
Summary of Learning outcomes 


## What is a database?
A database is a place where you can store, manipulate & retrieve data.Data is stored in tables in a database.

## What is a relational database?
A database with one or more relations between tables.

## What is SQL?
SQL(Structured Query Language) is a programming language used for communicating with database.It helps us to manage data held in a relational database.

## What is PostgreSQL?
PostgreSQL/Postgres is a free relational database management system. 

## Why learn PostgreSQL?
PostgreSQL is very popular among data scientists & other professionals working with data. It's free & easy to learn.

# [**Here**](https://www.postgresql.org/docs/9.3/installation.html) is how you can install PostgreSQL in your computer!

## How to connect to a database?
 * GUI client (not preferred even though it's easier way)
 * Using the Terminal/Command Line (Preferred because it lets you learn all the commands that your database requires to manipulate data)
 * Application (Writing a server site application & connect it to the database)
 
## What is database server & client?
A database server is a server which uses a database application that provides database services to other computer programs or to computers, as defined by the client–server model.The database client is a software that is used to connect with the database server and perform operations on the data. Many different types of database clients can connect with a database server.
The database client software can be desktop based or web based. It can be simple or extremely complex. It can be a GUI based client or a command based client. It can be a free or paid software.

## IDE
* Datagrip (best but paid; [here](https://www.jetbrains.com/help/datagrip/installation-guide.html#snap) is how you can install Datagrip)
* Postico (Free; Only for Mac users (https://eggerapps.at/postico/,"here") is how you can install Postico)
* pgAdmin (Free; Available for windows users)

## Set up PSQL (for windows)
[Here](https://www.microfocus.com/documentation/idol/IDOL_12_0/MediaServer/Guides/html/English/Content/Getting_Started/Configure/_TRN_Set_up_PostgreSQL.htm)

### SQL Commands/Operators

|                                                              |                                                                                |
| ------------------------------------------------------------ | ------------------------------------------------------------------------------ |
|  SELECT column1,column2 FROM table_name                     | returns columns/set of records from the tables of a database                   |
|  CREATE DATABASE database_name; (put the semi-colon)        | Creates a new databse                                                          |
|  DROP DATABASE database_name;                               | Deletes the database (Be aware while using it, removes all the data in seconds)|
|  CREATE table_name (                                        | Creates a table                                                                |
|         column_name + data type + constraints (if any)       |                                                                                |
|                  )                                           |                                                                                |
|  INSERT INTO table_name (column1, column2, column3, ...)    | Insert records                                                                 |
|  VALUES (value1, value2, value3, ...);                      |                                                                                |
|  SELECT * FROM table_name                                   | the * sign selects all the rows from the table                                 |
|  ORDER BY (SELECT * FROM table_name ORDER BY column ASC)    | Sorts the data                                                                 |
|    ASC (For ascending order)				       |										|
|    DESC (For descending order)			       |										|
|  DISTINCT 						       | Prevents showing the same records in a column					|
|   SELECT DISTINCT column FROM table ORDER BY column;         |										|
|  WHERE 						       | Shows the data according to preferred choice					|
| SELECT * FROM table 					       |										|
| WHERE column(e.g: gender) = 'record' (e.g: Female)            |										|
|  AND,OR 						       | Allows the user to test multiple conditions                                    |                      	
| WHERE condition1                                             |         (Be aware of the order of operation parantheses)                       |
| AND condition2                                               |                                                                                |
| ...                                                          |                                                                                |
| OR condition_n;                                              |                                                                                |
|  Comparison Operators (>,<,>=,<=,<>) ('<>' for Not equal)   |                                                                                |
|  LIMIT						       | Limits the number of shown rows						|				
| SELECT * FROM table_name LIMIT number_of_rows;	       | 	       									|
|  OFFSET (SELECT * FROM table OFFSET digit)		       | Only shows the rows after the 'digit' mentioned 				| 
|  FETCH (e.g: FETCH 5 ROWS ONLY)			       | Fetch only required data from the table					|
|  IN (value IN (value1,value2,...))                          | Replaces several OR/ANDs							|
|  BETWEEN 						       | Used to show records in a certain range					|
| e.g: SELECT * FROM table 				       |										|
| WHERE birthday BETWEEN DATE '2000-01-01' AND '2020-08-20';   |						       				|
|  LIKE/ILIKE (ILIKE isn't case sensitive') / (LIKE '---@%')  | Shows the records of specified characters. '%' is used as wildcard             | 	
|  GROUP BY                                                   | This along with the COUNT() function shows the grouped data			|
|  COUNT() / HAVING COUNT()                                   |										|
|		COALESCE(argument 1, argument 2....) 				        | The COALESCE function accepts an unlimited number of arguments.|
|                                                   |  It returns the first argument that is not null. If all arguments|
|                                                   |  are null, the COALESCE function will return null.     |                                                                    |  NULLIF()                                         | The NULLIF() function returns NULL if two expressions  |
|                                                   | are equal, otherwise it returns the first expression.  |
| NOW() /NOW():: time  (timestamp)    | Shows the actual time |
| SELECT NOW() - INTERVAL '10 Year'   | Shows the difference of date (e.g: here it shows the date of 10 years ago,'+' is used for future dates ) |
| SELECT EXTRACT(YEAR FROM NOW()) (YEAR/DAY/DOW-day of the week/CENTURY/MILISECOND)     | Extract a certain part of the date from a given year |
| ALTER    | Used for modifying data in a table |
| DELETE |  Deletes the data |
| UPDATE | Updates a row |
| (e.g: UPDATE table_name SET column_name = '...' WHERE id = 1) |                   |
| ON CONFLICT | can be used to specify an alternative action to raising a **unique** constraint or exclusion                              constraint violation error |
| JOIN | Joins two tables |
| LEFT JOIN | Joins two tables which have no foreign key relationship |




### Command line Utilities in PostgreSQL     
|                                                              |                                                                       |
| ------------------------------------------------------------ | ----------------------------------------------------------------------|
|  \?                                                         | shows all the commands                                                |
|  \l                                                         | to get the list of all available databases                            |
|  \dt                                                        | Enlists the available tables in the current database                  |
|  \c                                                         | Connects to another database                                          |
|  \d                                                         | List of visible tables,views and sequences                            |
|  \i 'C:/Users/Zaima Fariha/Downloads/person.sql'(filepath)  | Reads input from the file. (Must include the single quotation in the  |
|                                                              | address while working from windows)                                   | 
| \x     | Shows the expanded display |

# How to generate data without inserting them manually?
- Download the SQL database (Check out [this website](https://www.mockaroo.com/) for random data generation)
- use **\i 'filepath'** command 



# [Data Types](https://www.postgresql.org/docs/9.5/datatype.htm) in PostgreSQL

# UNIQUE Constraints
The UNIQUE constraint ensures that all values in a column are different.
SELECT column_name COUNT() FROM table_name GROUP BY column_name HAVING COUNT() > 1; - Helps the user to find a Duplicate 

# How to export query results to CSV?
- \copy table_name TO 'file path' DELIMITER ',' CSV HEADER ; 

# Notes:
- If a row already exists and has a primary key, manually inserting data in the same row will result in duplicate key violation.
- Constraints mean whether it's primary key,foreign key etc.
- Foreign keys can be only assigned when there is a relation between two tables 
