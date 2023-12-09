<p align="center">
<img src="https://github.com/riek10/owasp-juice-shop/assets/113129662/da1bbd79-3264-4da9-9019-01f16fda61e0"
 alt="Owasp Juice Shop logo"/>
</p>

<h1>Owasp Juice Shop- Web Application Security: Vulnerability testing </h1>
This tutorial goes through the various exploitations capable of being executed on Owasp juice Shop Web Application<br />

<h2>Environments and Technologies Used</h2>

- VirtualBox
- Zaproxy (ZAP)
- Juice Shop Web Application

<h2>Operating Systems Used </h2>

- Kali Linux</b> 

<h2>Vulnerability Testing & Enumeration</h2>

- Null Byte Bypass
- SQL Injection

<h2>Exploitations</h2>

<p>
<img src="https://github.com/riek10/owasp-juice-shop/assets/113129662/b9905956-50e5-484b-948f-752843d2b5a5" height="45%" width="45%"/>
<img src="https://github.com/riek10/owasp-juice-shop/assets/113129662/0270e8fe-e8c0-41d4-8b25-e221696e1e13" height="45%" width="45%"/>
<img src="https://github.com/riek10/owasp-juice-shop/assets/113129662/022afd5e-3953-4812-b142-a5ccff26c4af" height="45%" width="45%"/>

</p>
<p>
 The first vulnerability tested on the Juice Shop web application was a Null Byte Bypass. This technique allows you to input data that would otherwise be filtered out. This can be used to bypass upload restrictions or in this case, view a file that isn't viewable in its current format. I opted to use the Null Byte Character "%2500" to view the "Package.Json.bak" file that I discovered on the hidden FTP page. I used Zaproxy which is a web application scanner to change the parameters of package.json.bak file search and insert the bypass to gain access to the file. As you can see the null byte characters were able to trick the web application into thinking the JSON.bak file was instead a .md file which I could then view.
</p>
<br />

<p>
 <img src="https://github.com/riek10/owasp-juice-shop/assets/113129662/939ab272-8628-4141-b80b-ad73155397b2" height="45%" width="45%"/>
 <img src="https://github.com/riek10/owasp-juice-shop/assets/113129662/3a08a1d1-9034-417f-9b2c-f3f1b733ceaf" height="45%" width="45%"/>
 <img src="https://github.com/riek10/owasp-juice-shop/assets/113129662/b91488d9-9b60-43e7-b207-5440b2342100" height="45%" width="45%"/>
</p>

<p>
  For the next exploitation i decided to go with a basic SQL injection. SQL injection is an attack that uses malicious SQL code to access information that was not supposed to be viewable. In this instance i used the payload ('OR 1=1;--) with a "test" password in the user login field in order ot gain access to a user account. I was successful in gaining access and decided to add a new alert to ZAP that would notify me if any SQL Code was being entered in the login field.
</p>
