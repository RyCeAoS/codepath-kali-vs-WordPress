# Vulnerability 1 
# Authenticated Stored Cross-Site Scripting (XSS)

Description
-Authenticated Cross-Site Scripting (XSS) in post/page (text editor mode). Editor user and up.

Tested: Version 4.2.2
Fixed: Version 4.2.3
https://wordpress.org/news/2015/07/wordpress-4-2-3/

Steps in recreating the vulnerability
-Go to vulnerable site and see what version of WordPress it runs
-Check to see if the plugin allows comments
- if the ability to add comments is there, then add the code:
- ```<a href="[caption code=">]</a><a title=" onmouseover=alert('test')  ">link</a> ```
- if there is an alert that says test when hovering over the link then the website is vulnerable for Authenticated Stored Cross-Site Scripting

Gif walkthrough:
<img src="XSS HoverMouse.gif" alt="Authenticated Stored Cross-Site Scripting (XSS)">



# Vulnerability 2 
# Authenticated Stored XSS via Crafted Links

Description
-The function wp_targeted_link_rel() can be used in a particular way to result in a Stored Cross-Site Scripting (XSS) vulnerability.

Tested: Version 5.3
Fixed: Version 5.3.1
https://wordpress.org/news/2019/12/wordpress-5-3-1-security-and-maintenance-release/

Steps in recreating the vulnerability
-Go to vulnerable site and see what version of WordPress it runs
-Check to see if the plugin allows comments
- if the ability to add comments is there, then add the code:
- ``` <a href="#" title=" target='abc' rel= onmouseover=alert(/XSS/) ">This is a PoC for a Stored XSS</a> ```
- if there is a text box that says  the message within the alert parameter when hovering over the link then the website is vulnerable for Authenticated Stored Cross-Site Scripting via Crafted Links

Gif walkthrough:
<img src="XSS Authenticated Stored via Crafted Links.gif" alt="Authenticated Stored XSS via Crafted Links)">


# Vulnerability 3
# Authenticated Stored Cross-Site Scripting (XSS) in YouTube URL Embeds

Description
-This can be exploited by unauthenticated users in versions 4.7 and 4.7.1 by leveraging this vulnerability https://wpvulndb.com/vulnerabilities/8734

Tested: Version 4.0-4.7.2
Fixed: Version 4.7.3
https://wordpress.org/news/2019/12/wordpress-5-3-1-security-and-maintenance-release/

Steps in recreating the vulnerability
-Go to vulnerable site and see what version of WordPress it runs
-Check to see if the plugin allows comments
- if the ability to add comments is there, then add the code:
- ``` https://youtube[.]com/watch?v=abc<svg onload=alert(1)> ```
- if there is an alert after clicking the link then the website is vulnerable for Authenticated Stored Cross-Site Scripting (XSS) in YouTube URL Embeds

Gif walkthrough:
<img src="XSS Youtube Embedded Link.gif" alt="Authenticated Stored Cross-Site Scripting (XSS) in YouTube URL Embeds">




