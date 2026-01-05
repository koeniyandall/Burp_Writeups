# Username Authentication w/ Account Lock

This lab basically tries to enumerate a correct username by trying to find out which username locks. Meaning that our password was incorrect too many times.

# Method

1. We iterate through usernames but, using use a Null payload for the second payload position that we put after the password:

    username = $payload$, password=test$$

You can see we are not actually changing anything in the second payload, simply seeing which account will lock with multiple incorrect logins.

Now, we find that one of the usernames actually lock, meaning that it is associated with an actual account. Now to find the password we simply run a sniper attack for the password.
