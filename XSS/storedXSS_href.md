# Stored XSS into anchor href attribute with double quotes HTML-encoded

This lab requires you to inject javascript into an href attribute of a <a> tag.

# Method

As stated before, the href attribute allows for javascript to be put into it. So we can actually do something like

    javascript:alert(document.domain)

this allows us to insert this as our website link! This is stored XSS because this link will work across sessions and work for anyone who visits this page and clicks our link.
