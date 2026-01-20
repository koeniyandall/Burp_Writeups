# Simple Reflected XSS

Reflected XSS works in such a way where an attacker can poison a certain link. for example www.google.com/<script>alert(1)</script>, and send this to a victim. The victims' system will then execute this arbitrary javascript.

# Method

So for this, we see a search bar at the top of the page. If you search for something you can see that it says something along the lines of:

    0 results for [your search here]

This tells us that at least our query is used SOMEWHERE in the page and reflected in the DOM. So then we can simply test for XSS by just inserting a simple payload like 

    <script>alert(1)</script>

and this ends up working!
