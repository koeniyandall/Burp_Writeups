# File path traversal, traversal sequences blocked with absolute path bypass

This lab stops the attacker from doing path traversals by blocking  the ".." charcters.

# Method

This can be very easily bypassed by simply using the absolute path of the file for example:

    /etc/passwd

instead of 

    ../../etc/passwd

and the first way worked! So in the HTTP response we were return all passwords instead of simply the image.
