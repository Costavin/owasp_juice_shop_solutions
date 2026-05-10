# Weird Crypto

We need to report an erroneous use of a cryptographic algorithm, or library. In this case it has been pointed out that passwords must be salted before being hashed. That's because we easily retrieved the password for admin@juice-sh.op, as we found the MD5 hash in the JWT web token, that was "broke" by `john` with ease (over the notorious wordlist `rockyou.txt`).
