# View Basket   -   &#9733; &#9733;

From Burpsuite, we can intercept the `GET` and `POST` request at login. Once of these requests is related to the basket retrieval. We can notice that there is a `GET` request to the `/rest/basket/X` endpoint. So we can change the parameter `X` with whatever value, and try to look at baskets of other users. 
