# Login Amy

In the description of the task, it is hinted that Amy didn't read "One important final note". This note is related to how inefficient a one character padding might be. In this case, Amy followed the same suboptimal strategy by choosing a password padded with dots. This challeng is easily resolved by defining your own john-local.conf with the right rules. Another hint that can be extracted from the challenge is that Amy chose some password related to Kif. With some imagination we can apply some changes as we did with mr. McSafeSearch, and gain the password:

```
john --wordlist=/path/rockyou.txt --format=raw-md5  --rules:myrule hashes.txt
cat ~/.john/john.pot
```
