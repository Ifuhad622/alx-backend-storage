0x00. MySQL advanced 💻🧠
Back-end SQL MySQL

Concepts to Explore 🔍
Advanced SQL
Resources 📚
MySQL cheatsheet
MySQL Performance: How To Leverage MySQL Database Indexing
Stored Procedure
Triggers
Views
Functions and Operators
Trigger Syntax and Examples
CREATE TABLE Statement
CREATE PROCEDURE and CREATE FUNCTION Statements
CREATE INDEX Statement
CREATE VIEW Statement
Learning Objectives 🎯
General
Explain how to create tables with constraints
Optimize queries by adding indexes
Implement stored procedures and functions in MySQL
Implement views in MySQL
Implement triggers in MySQL
Requirements 📝
General
Execute files on Ubuntu 18.04 LTS using MySQL 5.7 (version 5.7.30)
End files with a new line
Add comments before SQL queries
Start files with a comment describing the task
Use uppercase for SQL keywords
Include a README.md file at the root of the project folder
Test file lengths using wc
More Info ℹ️
Comments for SQL files should be formatted as:
$ cat my_script.sql
-- Your SQL query here
Tasks 📋
Task 0. We are all unique! 🦄
Description: Create a table users with specified attributes

With these attributes:
id, integer, never null, auto increment and primary key
email, string (255 characters), never null and unique
name, string (255 characters)
If the table already exists, your script should not fail
Your script can be executed on any database
Context: Make an attribute unique directly in the table schema will enforced your business rules and avoid bugs in your application


Task 1. In and not out 💼
Description: Create a table users with additional attribute country

With these attributes:
id, integer, never null, auto increment and primary key
email, string (255 characters), never null and unique
name, string (255 characters)
country, enumeration of countries: US, CO and TN, never null (= default will be the first element of the enumeration, here US)
If the table already exists, your script should not fail
Your script can be executed on any database

Task 2. Best band ever! 🎸
Description: Rank country origins of bands by number of fans
Requirements:

Import this table dump: metal_bands.sql.zip (check link on your intranet)
Column names must be: origin and nb_fans
Your script can be executed on any database
Context: Calculate/compute something is always power intensive… better to distribute the load!


Task 3. Old school band 🎶
Description: List bands with Glam rock as their main style, ranked by longevity
Requirements:

Import this table dump: metal_bands.sql.zip(check link on your intranet)
Column names must be: band_name and lifespan (in years until 2022 - please use 2022 instead of YEAR(CURDATE()))
You should use attributes formed and split for computing the lifespan
Your script can be executed on any database

Task 4. Buy buy buy 💳
Description: Create a trigger to decrease item quantity after adding a new order
Quantity in the table items can be negative.
Context: Updating multiple tables for one action from your application can generate issue: network disconnection, crash, etc… to keep your data in a good shape, let MySQL do it for you!


Task 5. Email validation to sent 📧
Description: Create a trigger to reset valid_email attribute only when email has changed
Context: Nothing related to MySQL, but perfect for user email validation - distribute the logic to the database itself!


Task 6. Add bonus 🎉
Description: Create a stored procedure AddBonus to add a new correction for a student
Requirements:

Procedure AddBonus is taking 3 inputs (in this order):
user_id, a users.id value (you can assume user_id is linked to an existing users)
project_name, a new or already exists projects - if no projects.name found in the table, you should create it
score, the score value for the correction
Context: Write code in SQL is a nice level up!


7. Average score 📊
Description: Create a stored procedure ComputeAverageScoreForUser to compute and store the average score for a student
Requirements:

Procedure ComputeAverageScoreForUser is taking 1 input:
user_id, a users.id value (you can assume user_id is linked to an existing users)

8. Optimize simple search 🔍
Description: Create an index idx_name_first on the table names for the first letter of name
Requirements:

Import this table dump: names.sql.zip (check link on your intranet)
Only the first letter of name must be indexed
Context: Index is not the solution for any performance issue, but well used, it’s really powerful!


9. Optimize search and score 🔢
Description: Create an index idx_name_first_score on the table names for the first letter of name and score Requirements:

Import this table dump: names.sql.zip
Only the first letter of name AND score must be indexed

10. Safe divide 🛡️
Description: Create a function SafeDiv to divide two numbers safely
Requirements:

You must create a function
The function SafeDiv takes 2 arguments:
a, INT
b, INT
And returns a / b or 0 if b == 0

11. No table for a meeting 🚫
Description: Create a view need_meeting to list students with a score under 80 and no last meeting or more than 1 month
Requirements:

The view need_meeting should return all students name when:
They score are under (strict) to 80
AND no last_meeting date OR more than a month

12. Average weighted score 📊
Description: Create a stored procedure ComputeAverageWeightedScoreForUser that computes and stores the average weighted score for a student
Requirements:

Procedure ComputeAverageScoreForUser is taking 1 input:
user_id, a users.id value (you can assume user_id is linked to an existing users)
Tips:

Calculate-Weighted-Average

13. Average weighted score for all! 📊
Description: Create a stored procedure ComputeAverageWeightedScoreForUsers that computes and stores the average weighted score for all students
Requirements:

Procedure ComputeAverageWeightedScoreForUsers is not taking any input.
Tips:

Calculate-Weighted-Average
