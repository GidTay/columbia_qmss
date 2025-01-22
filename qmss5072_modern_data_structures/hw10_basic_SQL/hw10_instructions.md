# QMSS G5072 Homework 10
#### Thomas Brambor 

Practicing SQL Queries
============================

For this homework, we will be using the same connection as in lecture but rely on a different database called `witchcraft`. Use the information below to connect to the database.

  - MySQL database
  - user: `student`
  - password: `gues`
  - dbname: `witchcraft`
  - host: `columbia-mds-mysql.csbmzoea3lu9.us-east-1.rds.amazonaws.com`
  - port: `3306`

The data comes from a project on "Scottish Witchcraft" and contains all people known to have been accused of witchcraft in early modern Scotland. There is information on where and when they were accused, how they were tried, what their fate was etc.

>Julian Goodare, Lauren Martin, Joyce Miller and Louise Yeoman, ‘The Survey of Scottish Witchcraft’, http://www.shca.ed.ac.uk/Research/witches/) 

#### 1. Getting to know the data

a) Show all tables in the database.
b) Show the first three entries in the table `accused`.    
c) How many people are included in the accused table?   
d) Looks like the `age` is missing for some observations. Count the number of non-missing values for `age` in the data.  
e) Show a list of unique `occupation`s.
f) What proportion of accused are female?

#### 2. Seeing the Devil

Let's look at some appearances of the devil in the `devilappearance` table.

a) List the unique `devil_type`s in the data.  
b) There is also a little description of the type of the devil sighting in the `devil_text` column. How many of the sightings mention the word "black" in the description?
c) What proportion of the devils (in `devil_type`) are male? 

#### 3. The trial

Let's take a look at the information on the `trial`.

a) What are the average and maximum numbers of male and female accusers?  
b) Count the number of `sentence`s by sentence type. List them in a table (in descending order), excluding missing values. Rename the column headings to something sensible.  
c) Do the number of accusers matter for the `verdict`? Compare the average number of accusers by the type of verdict. Again make sure the table is sorted and the headings make sense. 

#### 4. Tortured Truth

a) Left join the `trial` and `confession` tables. For what share of trials does the database record confessions? Create a results table with the number of all trials, the number of confessions, and the share of trials with confessions recorded.

b) Only a small number of trials have records of torture. Is there a higher share of confessions among trials with records of torture than trials without such record? _Hint:_ You will need to merge on the `confession` table. 


### Submission

Please follow the [instructions](/Exercises/homework_submission_instructions.md) to submit your homework. The homework is due on Wednesday, November 20 at 5pm.
