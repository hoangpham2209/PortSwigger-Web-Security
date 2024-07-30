# Lab: SQL injection UNION attack, retrieving data from other tables

## Lab's description

This lab contains a SQL injection vulnerability in the product category filter. The results from the query are returned in the application's response, so you can use a UNION attack to retrieve data from other tables. To construct such an attack, you need to combine some of the techniques you learned in previous labs.

The database contains a different table called users, with columns called username and password.

**End goal:** Retrieves all usernames and passwords, and log in as the `administrator` user.

## Solution

First, I choose any type of category.

Now, I try to modify the link to determine the number of columns required.

After I try, I can see `' ORDER BY 3--` display error. That means it has 2 columns.

Now I determine which column is string data: `' UNION SELECT NULL,'a'--`

Now exploit the payload: `' UNION SELECT NULL, username || '~' || password FROM users--`

It will show you the username and password like this: `administrator~c33dy80c5hdjybojdbzf`, use it to log in and we done.

**Source:** [Lab: SQL injection UNION attack, retrieving data from other tables](https://portswigger.net/web-security/learning-paths/sql-injection/sql-injection-using-a-sql-injection-union-attack-to-retrieve-interesting-data/sql-injection/union-attacks/lab-retrieve-data-from-other-tables)
