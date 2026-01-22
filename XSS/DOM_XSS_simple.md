# DOM XSS in document.write sink using source location.search

In this lab, we are told that the website is weak against DOM based XSS in the search area of the website.

# Method

So, if we search anything at all, for example abd123 we need to check exactly where this goes in the DOM. If our user input is used directly in the HTML with no checks or sanitization, we can maybe close out some tags and insert our own tags.

Now, for this lab we see if we inspect element and look at the JS that its something along the lines of <img src="image.png + YOUR_QUERY"> This looks simple enough but if, in our search we do something like

    "><script>alert(document.write)</script>

Then we can break out. Some things we should make note of:

    window.location.search refers to, simply, anything after the ? in the URL

    
