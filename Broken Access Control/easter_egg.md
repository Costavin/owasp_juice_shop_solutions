# Easter Egg

If we open it, we suddenly notice it's a base64 encoded string.

`$ echo "L2d1ci9xcmlmL25lci9mYi9zaGFhbC9ndXJsL3V2cS9uYS9ybmZncmUvcnR0L2p2Z3V2YS9ndXIvcm5mZ3JlL3J0dA==" | base64 -d`

If we decrypt it, we find a list of strings slash separated. Since it looks like some directory, it might be worth to check for some shift cipher. It can be easily found that's the case for rot13.

