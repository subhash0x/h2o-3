# Security Policy

## Supported Versions

https://www.h2o.ai

Use this section to tell people about which versions of your project are
currently being supported with security updates.

| Version | Supported          |
| ------- | ------------------ |
| 5.1.x   | :white_check_mark: |
| 5.0.x   | :x:                |
| 4.0.x   | :white_check_mark: |
| < 4.0   | :x:                |

## Reporting a Vulnerability

hey h2o while going through your website I notice when I entering {{8*8}}  i got result 64 which mean your website is vulnerable to template injection.
Template Injection occurs when user input is embedded in a template in an unsafe manner.
Unsafely embedding user input in templates enables Server-Side Template Injection, a frequently critical vulnerability that is extremely easy to mistake for Cross-Site Scripting (XSS), or miss entirely. Unlike XSS, Template Injection can be used to directly attack web servers' internals and often obtain Remote Code Execution (RCE), turning every vulnerable application into a potential pivot point.
 
POC 

https://www.h2o.ai/?s=jack+{{constructor.constructor('alert(document.cookie)')()}}

https://www.h2o.ai/?s=jack+{{constructor.constructor('alert(2);alert(1);<script>window.location.replace("http://www.evil.com");</script>')()}}



How Can I Protect Web Applications From Server-Side Template Injections?

In order to protect against this kind of vulnerability, you should treat the string loading functionality with the same care as the eval function. Wherever possible, load static template files.
 
In addition, whenever you need to pass dynamic data to a template, don't do it directly within the template file, but use the template engine's built-in functionality to expand expressions to their result instead.

refer:- 
https://www.betterhacker.com/2018/12/rce-in-hubspot-with-el-injection-in-hubl.html?spref=tw

https://portswigger.net/research/server-side-template-injection

Thank you 
