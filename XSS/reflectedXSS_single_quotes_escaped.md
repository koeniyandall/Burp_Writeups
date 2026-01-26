# Reflected XSS into a JavaScript string with angle brackets and double quotes HTML encoded and single quotes escaped

Okay so this easilt was one of the most difficult labs, not out of the length of the payload but just because there's no resources at all to explain this concept well. So, in this lab when you try to break out of something with a simple method such as ` 'alert(1)// ` this does not work because, when we search this we see it becomes:

    ` var x =  ' \'alert(1) ' ` 

What basically happened was the devloper made it so that whenever there's a "risky" character, they simple add a backslash. NOW, this backslash basically says "hey interprit this next character literally. So the trick to this lab is... just add a backslash!!. Now this is confusing so ill explain thoroghly

1. OUR PAYLOAD IS: \'alert(1)//

2. Developer code catches our sneak single quote trying to escape the string so it adds the backslash

3. Our payload becomes \\'alert(1)//

4. THE SECOND PARSER comes along and actually attempt to read our string. NOTICE: THERE ARE NOW TWO CONSECUTIVE BACKSLASHES. This breaks the second parser because this parser will only interprit the next character as a literal if and only if THERES ONLY ONE backslash. 

5. The "search" become '\\' and we are able to break out!!
