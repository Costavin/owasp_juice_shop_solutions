# Password Strength

From the token value that we find in the Cookies, we can decrypt and find out the admin's password hash. By means of crackstation.com, or `john`, we can easily find the password that generates that hash value.

`$ john --wordlist=~/Sources/wordlists/wordlists/passwords/  passwords --format=Raw-MD5
`
