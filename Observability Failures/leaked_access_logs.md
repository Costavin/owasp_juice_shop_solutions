# Leaked Access Logs

We need to search a little bit on, the internet. As a hint, it is said that was involved some developer platform, which we may interpret as stack overflow. Then, by searching `access log juice shop stack overflow`, we come up with a result that asks for less verbosity on access logs with expressjs/morgan. If we look around long enough, we will bump into a `GET` request for a pass change. Once we recover the correct key, we can perform a spray attack on Burp Suite, having a fixed password, and cycling through the users we dumped from the database. Pay attention not to encode the payload. And pay attention to the extracted password, as some characters are url encoded, and need to be decoded back before the attack takes place.

