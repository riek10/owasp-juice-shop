<p align="center">
<img src="https://github.com/riek10/owasp-juice-shop/assets/113129662/da1bbd79-3264-4da9-9019-01f16fda61e0"
 alt="Owasp Juice Shop logo"/>
</p>

<h1>Owasp Juice Shop- Web Application Security: Vulnerability testing </h1>
This tutorial goes through the various vulnerabilities capable of being exploited in Owasp juice Shop Web Application<br />

<h2>Environments and Technologies Used</h2>

- VirtualBox
- Zaproxy (ZAP)
- Juice Shop Web Application

<h2>Operating Systems Used </h2>

- Kali Linux</b> 

<h2>Vulnerability Testing & Enumeration</h2>

- Null Byte Bypass
- 

<h2>Vulnerability Tests</h2>

<p>
<img src="https://github.com/riek10/owasp-juice-shop/assets/113129662/b9905956-50e5-484b-948f-752843d2b5a5" height="45%" width="45%"/>
<img src="https://github.com/riek10/owasp-juice-shop/assets/113129662/0270e8fe-e8c0-41d4-8b25-e221696e1e13" height="45%" width="45%"/>
<img src="https://github.com/riek10/owasp-juice-shop/assets/113129662/022afd5e-3953-4812-b142-a5ccff26c4af" height="45%" width="45%"/>

</p>
<p>
 The first vulnerability tested on the Juice Shop web application was a Null Byte Bypass. This technique allows you to input data that would otherwise be filtered out. This can be used to bypass upload restrictions or in this case, view a file that isn't viewable in its current format. I opted to use the Null Byte Character "%2500" to view the "Package.Json.bak" file that I discovered on the hidden FTP page. I used Zaproxy which is a web application scanner to change the parameters of package.json.bak file search and insert the bypass to gain access to the file. As you can see the null byte characters were able to trick the web application into thinking the JSON.bak file was instead a .md file which I could then view.
</p>
<br />
