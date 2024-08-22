
# Lab: Brute-forcing a stay-logged-in cookie

## Lab's description

This lab allows users to stay logged in even after they close their browser session. The cookie used to provide this functionality is vulnerable to brute-forcing.

**End goal:** brute-force Carlos's cookie to gain access to his "My account" page.

## Solution

Login as Wiener. We will see the `stay-logged-in` cookie.

Send this to `Intruder` and set the payload like this:

![](ing/2.png)

Go to `Settings` and `grep-match` the string `Update` and run attack 

Filter the `Update` column and we will see the result.

##Reference:** [Lab: Brute-forcing a stay-logged-in cookie](https://portswigger.net/web-security/learning-paths/authentication-vulnerabilities/vulnerabilities-in-other-authentication-mechanisms/authentication/other-mechanisms/lab-brute-forcing-a-stay-logged-in-cookie)
