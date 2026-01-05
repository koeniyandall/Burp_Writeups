# 2FA Broken Logic

Here in this lab, we abuse the 2fa property of a vulnrable website. It has a session cookie that keeps track of which user is being authenticated, however this is vulnrable for the fact that we are able to manipulate which user is stored under this cookie.

# Method

They key to this lab is to basically log in with our credentials to our account but when we go to do the 4 digit verification code, we set the cookie to carlos and then simply brute force the 4 digit verification vode. Then we will be logged in to carlos' account! The only possible issue with this is you need to make sure you have intercept on when you login because there is a GET request you need to modify because this is the request that decides which aaount the verification code is sent to (we need to send it to carlos' email).
