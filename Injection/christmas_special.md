# Christmas Special 

After we have identified which endpoint is susceptible to injection, we can ask for a list of removed objects, and see what pop up. The payload used to interrogate the database looks like `')%20and%20deletedat%20is%20not%20null);--a`, as it lists only the deleted items. We can notice that one of these it the Christmas special of 2014, which still exists in the DB. Then, we just add it to the basket by injecting the id of the item in the POST request related to item additions. 

```
POST /api/BasketItems/ HTTP/1.1
...
{"ProductId":10,"BasketId":"1","quantity":1}

```

Once we check it out, we solve the challenge.
