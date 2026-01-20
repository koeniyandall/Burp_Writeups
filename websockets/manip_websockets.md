# Manipulating WebSocket messages to exploit vulnerabilities

Websockets are basically a bidirectional channel of communication. Unlike HTTP request response flow, websockets are fully async and bidirectional. So, as you can imagine, we can use alot of the same techniques for websockets that we also use for HTTP request smuggling.

# Method

So, we have a live chat app and our messages are rendered in HTML. So, we can basically insert XSS in the message we send from the websocket to the server in the form offf
    
    {
        {message:"<img src=1 onerror='alert(1)'>"}
    }

and we can then see that on our website that we get an alert at the top of the screen.
