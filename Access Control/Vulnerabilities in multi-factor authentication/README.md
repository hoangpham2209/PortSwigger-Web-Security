# Lab: 2FA simple bypass

## Lab's description

This lab's two-factor authentication can be bypassed. You have already obtained a valid username and password, but do not have access to the user's 2FA verification code. 

Your credentials: wiener:peter
Victim's credentials carlos:montoya

**End goal:** access Carlos's account page.

## Solution

Login to your account and verify. Then log out.

Login to victim's account, change URL to `/my-account`.

**Reference:** [Lab: 2FA simple bypass](https://portswigger.net/web-security/learning-paths/authentication-vulnerabilities/vulnerabilities-in-multi-factor-authentication/authentication/multi-factor/lab-2fa-simple-bypass)

# Lab: 2FA broken logic

## Lab's description

This lab's two-factor authentication is vulnerable due to its flawed logic. 

**End goal:**  access Carlos's account page.

## Solution

log in with `wiener` account

send `POST` to `Intruder`

change `verify` to `carlos`

brufe-force `mfa-code` with `character set` `0123456789`

Because of using free version, it took me lots of time to brufe-force the security code.

**Reference:** [Lab: 2FA broken logic](https://portswigger.net/web-security/learning-paths/authentication-vulnerabilities/vulnerabilities-in-multi-factor-authentication/authentication/multi-factor/lab-2fa-broken-logic)






