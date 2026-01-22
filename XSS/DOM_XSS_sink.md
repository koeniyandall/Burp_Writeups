# DOM XSS in document.write sink using source location.search inside a select element

This one was difficult, the key of the entire lab was to realize where the SOURCE of this vulnerability actaully was located.

# Method

Sooo, we basically start off by trying to find the JS behind the check stock functionality. We see it, and it uses the storeId VERY unsafely to construct some HTML elements. My initial, incorrect, idea was to try and manipulate the HTTP request in a way that closes out the select element and then goes on to actually call alert(1). This was verryyyy incorrect though, because the JS explicity reads from window.search (which is the URL). So the HTTP request would most likely interact with the back end BUTTT by changing the URL (where the JS actually takes from) then we can manipulate the page and run the JS in the same idea as before.
