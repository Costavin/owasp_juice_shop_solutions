# NoSQL Manipulation

We are asked to modify different reviews at once. We also know that product reviews are managed by a different database, because we cannot find any table related to product reviews when we exfiltrated the database. From burpsuite we can notice that, when we add some reviews, we `PUT` data at the endpoint `/rest/products/XX/reviews`, where XX is the product id. While we can fetch all the reviews for a particular product XX by sending a `GET` request. Unfortunately, removing the product id XX doesn't allow us to retrieve all the reviews. However, with `OPTIONS` request we can see other request we can use for that endpoint. SInce the challenge is an is related to a modification of reviews, the `UPDATE` request pops up at our eyes. A typical nosql payload that gathers more results makes use of equality, or inequality operators, as `$ne`. At the end we can patch the products with the following `JSON` payload:

```
{"id":{"$ne":"-1"},"author":"jim@juice-sh.op"}
```
