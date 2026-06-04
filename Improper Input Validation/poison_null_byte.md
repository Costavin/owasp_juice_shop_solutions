# Poison Null Byte

Since the files in the directory `ftp` can be accessed only if they have an extension .md or .pdf, then it is needed to fool the server into thinking we are requesting a file with such an extension. This can be achieved by appending the extension .md, to a special character that might be interpreted in an ambiguous way by the backend. If we suppose that the backand is a PHP application, then we can append the character "%00", which in the frontend is interpreted as 3 characters, but in the backhand it gets interpreted as a space, breaking the file up until the space character. As we have to take into account for URL encoding, we must encode it into %2500.

## Remedation

This kind of error usually occurs when a particular character is interpreted in two different ways in back and fronted. Since at the front end can still be bypassed, it must be addeded an additional layer into the backend that sanitizes the file requests, and reject the ones that do not follow the rules.
