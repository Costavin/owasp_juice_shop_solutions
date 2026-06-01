# Login Admin   -   &#9733; &#9733;

Since we don't know the password for the administrator account, we can try with some SQLi!
By looking around in the main page, we can notice that an account named admin@juice-sh.op left some reviews here and there.

Lets try to inject the password field with the payload `' or 1=1;--a`, with the `admin@juice-sh.op` in the username.
However the form will notify us that we've inserted an invalid username or password.
Lets try to inject the email then with payload `admin@juice-sh.op' or 1=1;--a` with any value for the password.
And we are in!

The injection would have also worked if in the username field we insert the payload `admin' or 1=1;--a`, or simply `' or 1=1;--a`. That's because it happened that the first retrieved account coincides with the first created account, which is in fact the administrator itself.

From the score-board page, we can notice by patching the vulnerability that the executed code line is:

`models.sequelize.query("SELECT * FROM Users WHERE email = '${req.body.email || ''}' AND password = '${security.hash(req.body.password || '')}' AND deletedAt IS NULL", { model: UserModel, plain: true })`

Where it can be noticed that our attempt to inject the password field was thwarthed by the security.hash() function.
