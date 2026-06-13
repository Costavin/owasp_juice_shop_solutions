# Access Log

Here we are requested to get access to any log file of the server. However, at first glance,  with a simple fuzzing process we didn't notice any particular log directoy. As a hint, it is suggested to go deeper. Then we might perform a deeper search, cycling over 2 dictionaries:

```
ffuf -u http://localhost:3000/FUZZ1/FUZZ2 -w dictionary_1.txt:FUZZ1 -w dictionary_2.txt:FUZZ2 -fs 75002 -rate 10
```

Then we will get a match, and access a log file.
