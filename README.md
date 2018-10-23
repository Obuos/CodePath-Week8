# Project 8 - Pentesting Live Targets

Time spent: **X** hours spent in total

> Objective: Identify vulnerabilities in three different versions of the Globitek website: blue, green, and red.

The six possible exploits are:
* Username Enumeration
* Insecure Direct Object Reference (IDOR)
* SQL Injection (SQLi)
* Cross-Site Scripting (XSS)
* Cross-Site Request Forgery (CSRF)
* Session Hijacking/Fixation

Each version of the site has been given two of the six vulnerabilities. (In other words, all six of the exploits should be assignable to one of the sites.)

## Blue

Vulnerability #1: SQL Injection (SQLi); when inserting ' OR SLEEP(5)=0--' onto the end of a salesperson URL the site will sleep for 5 seconds.

GIF: ![](https://github.com/Obuos/CodePath-Week8/blob/master/week8blue1.gif)

Vulnerability #2: Session Hijaking/ Fixation; the session ID of a logged in browser can be used from on a different browser, I used an incognito session of Chrome and a regular Chrome browser, now use the session ID into the new browser and sign back in. Admin access is no available.

GIF: ![](https://github.com/Obuos/CodePath-Week8/blob/master/week8blue2.gif)

## Green

Vulnerability #1: Cross-Site Scripting (XSS); On the public site, after submitting a feedback form including this script <script>alert('xss found');</script>. The user can find an XSS attack when opening the feedback section.

GIF: ![](https://github.com/Obuos/CodePath-Week8/blob/master/week8green1.gif)

Vulnerability #2: User Enumeration; When attempting to login on a valid account with an incorrect username, the error message "Log in was unsuccessful" will appear as bold. However, if the login id was invalid the message will not be bolded, thus revealing valid user ids.
The error the developer made was having custom styling error based on login types.

GIF: ![](https://github.com/Obuos/CodePath-Week8/blob/master/week8green2.gif)

## Red

Vulnerability #1: Cross-Site Request Forgery (CSRF); The CSRF token visible when inspected is not used as any user is able to edit freely, no permissions whatsoever is being asked.

GIF: ![](https://github.com/Obuos/CodePath-Week8/blob/master/week8red1.gif)

Vulnerability #2: Insecure Direct Object Reference (IDOR); Given the two hidden users from the Session Hijaking in Blue site, the user pages for these admin only pages can be found by changing the id="" at the end of the URL for the red site only.

GIF: ![](https://github.com/Obuos/CodePath-Week8/blob/master/week8red2.gif)


## Notes

Describe any challenges encountered while doing the work
