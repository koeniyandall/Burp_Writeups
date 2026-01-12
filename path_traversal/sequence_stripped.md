# File path traversal, traversal sequences stripped non recursively

On this lab things like ../ are stripped HOWEVER, if it simply does a single pass, we can kind of trick the software and does something like:

    ....//

This way, when the ../ is stripped we still have ../ so we can still traverse anywhere we want.

# Method

This lab is pretty simple, basically just highlighting the fact that there can be vulnrable software that checks the path and there are definitel ways to get past it if the developers are not thorough.
