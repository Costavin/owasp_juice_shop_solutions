# Weird Crypto

We need to report an erroneous use of a cryptographic algorithm, or library. In this case it has been pointed out that passwords must be salted before being hashed. That's because we easily retrieved the password for admin@juice-sh.op, as we found some MD5 hashes in the JWT web token, that were "broken" by `john` with ease (over the notorious wordlist `rockyou.txt`).
