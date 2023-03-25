---
title: "SQL for dummies"
date: 2023-03-25T12:55:37+05:30
draft: false
---

- SQL (Structured Query Language) is a declarative programming language used to manage databases
- It is sequential
- Each command is terminated by a semicolon ( ; )
- A command can aquire more than one line as long as it ends with a semicolon ( ; )
- It is not case sensitive (unlike JAVA)
— You can type the commands in uppercase or lowercase but the names that you give have to be in the correct case. (Commands are usually written in uppercase but don't be surprised if you find lowercase)

![Data Types](/DataTypes.png)

- These SQL commands are mainly categorised into four categories as:
    
    (i) DDL – Data Definition Language

    (ii) DQL – Data Query Language

    (iii) DML – Data Manipulation Language

    (iv) DCL – Data Control Language

**Initialisation of a Database**

```sql
-- This is how single line comments are added in SQL
/*
This can be used
for comments 
on multiple lines.
*/
CREATE DATABASE bandbooking;
CREATE TABLE Band(
    BandName varChar(22),
    NumberOfMembers integer);
ALTER TABLE Band ADD PRIMARY KEY (BandName);
ALTER TABLE Band-Booking ADD FOREIGN KEY (BandName REFERENCES Band(BandName);
```

What every line means:

1. The `CREATE DATABASE` command creates a database named “bandbooking”
2. The `CREATE TABLE` command creates a new table named “Band”
    - In parentheses, the fields are coded in
    - Each field is separated by comma
    - Two fields (BandName, Number of members) are given their data types (varchar(25), integer)
3. The `ALTER TABLE` command is used to add a primary key and the table name and the field name is specified (in parentheses)
4. The `ALTER TABLE` command is used to assign a new foreign key to another table (not created in this code “Band-Booking”) named “Band-Booking”. The keyword `REFRENCES` is used to locate the field and the table in which this field (BandName) is present and acting as a primary key.

**Populating a table with data**

```sql
--Both the lines of code do the same dthing but using different methods.
INSERT INTO Band ('The Local Train', 5);

INSERT INTO Band (BandName, NumberOfMembers)
VALUES ('The Local Train', 5);
```

What each line means:

1. The command `INSERT INTO` is used on the table Band to add two values to two fields
    - The names of the fields is not mentioned because SQL presumes the field inputs are arranged in order.
    - This is the shorthand of writing `line 2` and only used when you are VERY familiar with the table (knowing where fields are)
2. The same command `INSERT INTO` has been used, however this time the field names have been mentioned and the values corresponding to the fields have been added using the keyword `VALUES`
    - This is a safer way to do `Line 1`

**Making a query from the database**

```sql
--The main use of SQL (most important)
--Both the lines do the same thing
SELECT BandName, NumberOfMembers
FROM Band;

SELECT * FROM Band;
```

What each line does:

1. The `SELECT` command selects the two field (separated by a comma) from the table “Band” using the `FROM` keyword.
2. The `*` operator selects (using the `SELECT` command) everything from (using the `FROM` keyword again) the table “Band”


💡 Because the table “Band” (see code example 1 ‘Initialisation of Database’) has only two fields, “`*`” operator works perfectly here.


```sql
--Both lines do the same thing
SELECT BandName, NumberOfMembers
FROM Band
ORDER BY BandName;

SELECT BandName, NumberOfMembers
FROM Band
ORDER BY BandName asc; --Alternatively, you can use "dsc" to denote decending order
```

What each line does:

1. This line is used to select two fields, “BandName” and “NumberOfMembers”, from the table “Band”
    - The operator `ORDER BY` makes sure that the values given for the field “BandName” are ordered, in this case, by ascending order
2. This line does the same except uses the keyword `asc`.


🔑 The use of `asc` is purely optional, while the use of of `desc` is important. It makes sure the values are arranged in descending order.




💡 For integers and floating point values, ascending means that the lowest value comes first and descending means the opposite. Whereas for strings, ascending refers to alphabetical order and descending the opposite.


```sql
SELECT BandName
FROM Band-Booking
GROUP BY BandName;
```

The field ‘BandName’ in the table ‘Band-Booking’ might have repeated names of bands. For example-

TABLE➖ Band-Booking

| BandMemberName | BandName |
| --- | --- |
| CoolDude29 | CoolDudezz |
| RockHard | CoolDudezz |
| BigSean | ITWitzz |
| BanjoMan | SideTrack |

In the above table, one band name is repeated twice. When query will be done to select (with the `SELECT` command) for BandName, ‘CoolDudezz’ will be repeated. To make the query output more readable, we use `GROUP BY`. This will remove all redundancies and only show all the different bands that are there.

What each line does:

1. Selects field ‘BandName’
2. Selects from table ‘Band-Booking’
3. Groups by (removes redundancies in) the field ‘BandName’


💡 In some ways, `GROUP BY` alters the query output so that the field given to `GROUP BY` becomes the output’s primary key.



```sql
SELECT BandName, NumberOfMembers
FROM Band
WHERE NumberOfMembers > 2
ORDER BY BandName
```

What each line does:

1. Selects two fields, ‘BandName’ and ‘NumberOfMembers’
2. Selects from table ‘Band’
3. Uses `WHERE` operator to add conditions to the query. Adds the condition that the integer value in field ‘NumberOfMembers’ should be greater than 2
4. Orders by BandName (no repeating band names)

**Functions in SQL**

```sql
SELECT count(*)
FROM Band;

SELECT AVG(NumberOfMembers)
FROM Band;

SELECT SUM(NumberOfMembers)
FROM Band;

SELECT VenueName, Date
FROM Booking, Band-Booking
WHERE Band-Booking.BookingID = Booking.BookingID
AND Band-Booking.BandName = 'ComputerKidz';
```

What each like does:

1. Counts ALL (because of `*`) records from the table ‘Band’
2. Finds the average(mean) of all the values from field ‘NumberOfMembers’ from table ‘Band’
3. Sums up all the values from field ‘NumberOfMembers’ from table ‘Band’
4. Selects fields ‘VenueName’ and ‘Date’
5. Selects from table ‘Booking’
6. CHECKS (for every ‘VenueName’ and ‘Date’) if the field ‘BookingID’ from A DIFFERENT TABLE ‘Band-Booking’ has the same value as the ‘BookingID’ from the table ‘Booking’
7. AND checks if the ‘BandName’ from A DIFFERENT TABLE ‘Band-Booking’ has the string value ‘ComputerKidz’


💡 `[DifferentTableName.FieldName]` is the syntax we follow for “join condition”. This is used to get and check information from a table which is present in the same database but not in the table you selected from (using the `SELECT field FROM Table` command). This could be tricky so you must take care here


💡 Some older versions of SQL required you to use “INNER JOIN” everywhere. So for a simple:
`SELECT AVG(NumberOfMembers) FROM Band`
Became:
`SELECT AVG(Band.NumberOfMembers) FROM Band`
This format is not important for usage anymore for a lot of years.



**Updating and Deleting Tables**

```sql
UPDATE Band
SET NumberOfMembers = 6
WHERE BandName = 'ComputerKidz';
```

What this code does:

1. Finds, in the table ‘Band’, the record where the field ‘BandName’ has the varchar(25) value ‘ComputerKidz’
2. It finds the field ‘NumberOfMembers’
3. UPDATES (using the `UPDATE` command) the value of ‘NumberOfMembers’ to the integer 6

```sql
DELETE FROM Band-Booking
WHERE BandName = 'ITWizz';

DELETE FROM Band
WHERE BandName = 'ITWizz';
```

What this code does:

1. Deletes (using the `DELETE FROM` command) the record where the BandName had the varchar(25) value of ‘ITWizz’ from the table ‘Band-Booking’
2. Deletes the record where the BandName value is varchar(25) ‘ITWizz’ from the table ‘Band’

> This code is trying delete all the data about ‘ITWizz’ from the entire database.
> 

---

[SQL Murder Mystery](https://mystery.knightlab.com/)

If you feel like, you’ve got a hold of SQL now. Head over to the SQL Murder Mystery to solve a fun yet simple SQL puzzle.