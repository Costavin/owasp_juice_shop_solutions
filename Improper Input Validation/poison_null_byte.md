# Poison Null Byte

Since the files in the directory `ftp` can be accessed only if they have an extension .md or .pdf, it is needed to fool the server into thinking we are requesting a file with such extension. This can be achieved by appending the extension .md, appended to a character that might be interpreted in an ambiguous way by the backend (for e.g. a PHP application), that is %00. As we have to take into account for URL encoding, so %2500. 
