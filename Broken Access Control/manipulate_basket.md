# Manipulate Basket

If we intercept the requests related to the additon of items into the basket, we can notice it is firt submitted a GET request - `GET /rest/basket/X`, with X as the basket id of the user, followed by a POST request - `POST /api/BasketItems/` with the following body:

```
{
    "ProductId":39,
    "BasketId":"X",
    "quantity":1
}
```

However, if we try to change the value of BasketId and send it again, we notice we get and authorization error. Then there is some checking mechanism in place after all. However, since JSON is what it is, we can add another field BasketId with another value, and bypass the check. We can notice by swapping the position of the two Ids, that the check is not pplied to the whole argument of the requests, but stops at the first match.

```
{
    "ProductId":39,
    "BasketId":"X",
    "quantity":1,
    "BasketId":"Y"
}
```

Of course both X and Y must be valid BaskedIds.

## Remediation

One possible remediation is to first check the whole argument of the request, and do not stop only at the first match. It is always better a little bit conservative and safe, than sorry. Also, identifying duplicated fields in the same request might also raise a red flag.
