# Lab: SQL injection UNION attack, finding a column containing text

## Lab's description
This lab contains a SQL injection vulnerability in the product category filter. The results from the query are returned in the application's response, so you can use a UNION attack to retrieve data from other tables. To construct such an attack, you first need to determine the number of columns returned by the query. You can do this using a technique you learned in a previous lab. The next step is to identify a column that is compatible with string data.

**End goal:** determine which columns are compatible with string data.

## Solution

First, I choose any type of category `https://0ab6002803a5365c8256ddef0096004b.web-security-academy.net/filter?category=Lifestyle`

Now, I try to modify the link to determine the number of columns required.

After I try, I can see `' ORDER BY 4--` display error. That means it has 3 columns. So instead of: `' UNION SELECT NULL, NULL, NULL--`

I can use: `'+UNION+SELECT+NULL,'a',NULL--` to retrieve string data column.

**Source:** [Lab: SQL injection UNION attack, finding a column containing text](https://portswigger.net/web-security/learning-paths/sql-injection/sql-injection-finding-columns-with-a-useful-data-type/sql-injection/union-attacks/lab-find-column-containing-text)
