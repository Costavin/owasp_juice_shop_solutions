# Expired Coupon

If we search for the word `coupon` in the sources, we will bump into a list of old coupons, of which, the highest one dates back to the 2019. In fact, if we try to redeem it, we will fail miserably. However we can notice that no `POST` (or any( request is sent to the server. Thus it's safe to assume that's a check performed on client side. We can try to modify the system date to try to bypass the check in place. In fact, if we keep on searching other matches, we can find the excat checking process that is performed on coupons, in correspondence to applyCoupon() function.

```
sudo timedatectl set-ntp no
sudo date -s "20XX-XX-XX 12:00:00"
```

After that, we can reedem the coupon, and check out the cart, successfully solving the problem.

P.S.: reminder to set back to the current date - `sudo timedatectl set-ntp yes`
