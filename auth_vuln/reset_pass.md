# Password reset broken logic

In this lab you have to exploit a password reset functionality on the website.

# Method

The solution to this is basically getting a valid password reset token by trying to reset your own password, getting your own password reset code and then whenever you see the request for changing the password you can simply change the username so that you change carlos' account. This vulnerability is due to the fact that the backend doesnt make any validation on whether that reset cookie is associated with that username, allowing us to basically reset any account we want.
