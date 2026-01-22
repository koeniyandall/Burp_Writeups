# Reflected XSS into attribute with angle brackets HTML-encoded

So for this lab, we are looking a vulnerable search functionaly (we are told this info). The angled brackets do now work in that case at all.

# Method

Another method other than simply trying to close the brackets would be to try and actually close the attribute and create an attribute of our own. Many attributes would allow use to run JS. One such attribute being onfocus. We can kind of trick the system by doing something like

    " autofocus onfocus=alert(1) x="

the first quote is to make sure the other attribute closes and then we go on our enable autofocus and then say onfocus=alert() so as you can see, onfocus will always run. We then close with x= to make sure nothing breaks
