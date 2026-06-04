# Database schema 

After having identified the the field susceptible to sql injection, we can retrieve the entire database schema through the payload `aaaaa'))%20union%20select%20sql,1,2,3,4,5,6,7,8%20from%20sqlite_schema;--a`

## Remediation

Never trust the user inputs. If there is some parameter that is user controlled, it is a must to sanitize such inputs.
