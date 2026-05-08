# Error Handling

This error can be triggered with different payloads in multiple instances. For example, at the login, it can be tried to insert the character `'` in the username and password fields. The character itself tests the presence of a SQLi vulnerability, and the server responds with:

`[object Object]`


