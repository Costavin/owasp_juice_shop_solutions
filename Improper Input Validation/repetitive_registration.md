# Repetitive Registration

By following the DRY principle (Don't Repeat Yourself), we must not repeat our input field in the register form. 
It can also be accomplished by intercepting the `POST` request for a user registration, and resend the same request with `Repeat Password` empty (and a new email).

`{"email":"c@c.com","password":"11111","passwordRepeat":"","securityQuestion":{"id":2,"question":"Mother's maiden name?","createdAt":"2026-05-09T04:49:52.741Z","updatedAt":"2026-05-09T04:49:52.741Z"},"securityAnswer":"1"}`



