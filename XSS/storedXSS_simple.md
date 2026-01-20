# Simple Stored XSS

So for a stored XSS vuln, it differs from a reflected XSS attack such that instead of a user having to visit a specific link for the XSS to work, they simply have to visit ageneric page, because the backend will do the work of serving the malicious javascript.

# Method

This lab is very similar to the other one. All you do is make a comment and in the body of the comment you simply insert

    <script>alert(1)</script>

this will actually alert ANYONE who visits this page. This is because the backend will serve our comment every single time the page is loaded by anybody, making this a much more deadly attack that reflected XSS.
