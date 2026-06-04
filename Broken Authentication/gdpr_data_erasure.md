# GDPR Data Erasure

Once we identified the target account, possibly after the database dump, we can login in with that account by using SQLi.
In the login page, we send in the `POST` request, the following payload:

```
{"email":"chris.pike@juice-sh.op' and 1=1;--a","password":"1"}
```

## Remediation

Once an account is disabled, it is suggested to remove/delete it completely from the database. Otherwise it will offer additional attacking ground to a malicious user.
