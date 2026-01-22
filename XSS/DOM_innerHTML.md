# DOM XSS in innerHTML sink using source location.search

In this lab, innerHTML is used! This poses some problems, one of them being that <script> </script> tags are not allowed inside of these things like headers. therefore, was can close out the </span> tag and then just use something like the following

    "></span><img src=1 onerror=alert(1)>

this ends up working. This just shows the importance of always knowing where and how your search and attack is being injested by the target.
