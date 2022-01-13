# Broken brute-force protection, IP block

## Task
This lab is vulnerable due to a logic flaw in its password brute-force protection. To solve the lab, brute-force the victim's password, then log in and access their account page.
-   Your credentials: `wiener:peter`
-   Victim's username: `carlos`

## Solution
I captured the request to the endpoint **/login** and, using Intruder, I started the attack:
- the first payload list, associated with the **username** contained "carlos" on every line, but, on every third line the username was "wiener"
- the second payload list, associated with the **password** contained the given password list, but, on every third line the password was "peter"

The reason I did that was to make sure after 2 incorrect login attempts I would login succesufly, becasue the server would block my IP for 1 minute if I did three consecutive incorrect attempts.
In the end, the credentials were `carlos:thomas`