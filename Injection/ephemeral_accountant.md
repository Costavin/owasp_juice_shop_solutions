# Ephemeral Accountant

Since we are not allowed to register the target user `acc0unt4nt@juice-sh.op` into the database, we need to "temporarily" create one. Then, we will need to exploit the already exixting vulnerability in the login page. Since the user does not exists, we can close the internal query by the usual character `'`, and add our pyaload through the key word `UNION`. In the second part, we need to match our target account, with some twists:

```
"'union select 2,'acc0unt4nt@juice-sh.op','acc0unt4nt@juice-sh.op',12345,'accounting','2','1.2.3.4','/assets/public/images/uploads/default.svg','',1,'2026-06-04 10:15:19.643 +00:00','2026-06-04 10:15:19.643 +00:00','null';--a"
```

The challenge goes through only if as role it is selected the right `accounting` role; another important nuance, is that, since the account does not exists, it must be chosen an id address that falls into the range `[1,20]`, range found previously by exfiltrating the whole users list.

## Remediation

Since user inputs can never be trusted, it is needed to parameterized queries, or prepared statements. In such a way, user inputs don't affect directly the query, and through substition parameters they are plugged into the query.

