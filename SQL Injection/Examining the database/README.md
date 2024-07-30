# Lab: SQL injection attack, querying the database type and version on MySQL and Microsoft

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
