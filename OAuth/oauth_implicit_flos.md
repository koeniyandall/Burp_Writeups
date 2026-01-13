# Authentication bypass via OAuth implicit flow

This lab shows a very critical bug in its Oauth integration, allowing the user to intercept the HTTP POST request and manipulate the email to log in to any arbitrary account it wants.

# Method

To solve this lab, we basically use our real credentials, wiener:peter to authenticate via OAuth. After this, we can simply look at the HTTP history and see a POST /authenticate request. We simply change the email in the JSON blurb at the bottom of the request and it works! We then have access to the account associated with Carlos' account
