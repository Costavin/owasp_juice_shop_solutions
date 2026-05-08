# Securiy Through Obscurity

This achievement is unlocked once you read the contents of the `encrypt.pyc` file located in `ftp`. As it is a compiled bytecode file, we need some decompiler to revert it back, for example `pycdc`. We learn that it performs an encryption in a RSA fashion-like. Luckily for us, the message was not encrypted as a whole, but character by character. So, what we have, is a sort of hash for key char. So, instead of reventing back the encrypt characters, we can encrypt all the ASCII characters, and map them back to their respective character:

```python
N = N   #substitute accordingly
e = e   #substitute accordingly
alphabet = dict()
for i in range(2,128):
    alphabet[str(pow(i,e,N))] = i

print(alphabet)
encrypted_document = open('announcement_encrypted.md', 'r')

result = ""
for line in encrypted_document.read().split('\n'):
    if line in alphabet:
        result += str(chr(alphabet[line]))
print(result)

```
