# Mystery Lab 1

I started off this mystery lab by simply looking around the website and analyzing the HTTP request made as I clicked different buttons. One thing that stuck out to me was the "check stock" button. This checked a certain stock via an api url. This, in essence was the URL the server made a request to to check the stock of a product

# Exploit

We found an area that we, the attacker, can change and the server will simply make a request on our behalf. Soooo, if we decode the URL it uses in the requests themselves, we see it uses the IP address 192.168.0.X sooo, we then use burp intruder to basically enumerate every IP address in the range from 1-255. We find that one of the IP addresses returned 404 NOT FOUND instead of 400. So then we try and use 

    192.168.0.56

to then see if this houses /admin (which it does). Now that weve done that, it's as simple as adding in delete?username=carlos and we have then deleted carlos as a user or rather the server did.
