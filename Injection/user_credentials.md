# User Credentials

Once we found the field related to sql injection (linked to the `SELECT` key word), we can use this field to exfiltrate all the registered users. From the database schema we know the table name, and we already know how many fields we can at most retrieve (or pad eventually).
One payload that can exfiltrate the users is:

```
aaaaa'))%20union%20select%20id,username,email,password,totpSecret,isActive,createdAt,updatedAt,deletedAt%20from%20Users;--a
```

## Remediation

Since user inputs can never be trusted, it is needed to parameterized queries, or prepared statements. In such a way, user inputs don't affect directly the query, and through substition parameters they are plugged into the query.
