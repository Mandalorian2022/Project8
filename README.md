# Project 9 - Pentesting Live Targets

Time spent: **10** hours spent in total

> Objective: Identify vulnerabilities in three different versions of the Globitek website: blue, green, and red.

The six possible exploits are:

* Username Enumeration
* Insecure Direct Object Reference (IDOR)
* SQL Injection (SQLi)
* Cross-Site Scripting (XSS)
* Cross-Site Request Forgery (CSRF)
* Session Hijacking/Fixation

Each color is vulnerable to only 2 of the 6 possible exploits. First discover which color has the specific vulnerability, then write a short description of how to exploit it, and finally demonstrate it using screenshots compiled into a GIF.

## Blue

Vulnerability #1: SQL Injection

Description:

For this vulnerability I tried to inject couple simple commands such as such as ``admin` --`` , ``' or 1=1#``on the ``/blue/public/salesperson.php?id=`` directory. Overall, the ``sleep`` command seemed more vulnurble due to the page response time. ``' OR SLEEP(5)=0--'`` command increased the response time of the webpage by 5-10 second from regular request. Therefore it is vulnurble to SQL Injection and data exfiltration.
![blue-vuln](https://user-images.githubusercontent.com/96266650/164789099-21e1c49b-6af2-4a0e-b3d8-04ba049e74c6.gif)



## Green

Vulnerability #1: Cross-Site Scripting (XSS)

Description:

For this vulnerability, I took an advantage of the contact us section to try some malicious code. First I tried a very basic ``alert`` script in contact us section, and I went back to the admin section to view the script and found out that it is vulnrble to cross-site scripting.

![green-vuln1](https://user-images.githubusercontent.com/96266650/164801265-171fdf76-7904-4e56-9017-38f71d424db6.gif)

![green-vuln-2](https://user-images.githubusercontent.com/96266650/164801280-66bb34bb-c067-4395-a6dc-f1db9ab4e8e7.png)



## Red

Vulnerability #1: Insecure Direct Object Reference (IDOR)

Description:
For this vulnerability I have discovered that there are no input check for userID in ``/red/public/salesperson.php?id=`` section. I tried user ``11`` and the site showed me the information that is visible in ``/red/public/territories.php`` directory.


![red-vuln1](https://user-images.githubusercontent.com/96266650/164802192-3c807ff1-6c4b-44d2-b582-1db266b24801.gif)


## Notes

These demonstration were made for educational purposes only. 

List of Targets:
Mirror 1	https://35.184.88.145/
Mirror 2	https://104.198.208.81/
