# Notes on websockets

A websocket, WS, is basically just another form of communication between computers. Unlike HTTP however, WS are completely async and bidirectional. This allows for faster and more efficient communication. WS are great for things like video games or live chat messages that require a constant two way flow of information.

### How do websockets work

    1.You start by sending an HTTP request to the tune of "upgrade: websocket".

    2.Persistent TCP link

    3.Bidirectional communication

    4.No repeated HTTP headers only message data

    5.The connection stays open until either side closes it

### When not to use a websocket

If we want to fetch old data, or want to get the data only once to process it with an application, HTTP is the better option. 
