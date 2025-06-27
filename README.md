
Creating Vulnerability Assessment with help of 2 VM's Kali and Metasploit inside VirtualBox using Nmap Scanner
<h1>Vulnerablity-assesment</h1>



<h2>Description</h2>
 hands-on program covering key cybersecurity skills including threat detection, network security, Linux, SQL, SIEM tools, incident response, and security best practices. Completed practical labs using tools like Wireshark and Qwiklabs to simulate real-world scenarios.
<br />


<h2>VM and Utilities Used</h2>

- <b>Kali</b> 
- <b>Metasploit</b>

<h2>Environments Used </h2>

- <b>Windows 10</b> 

<h2>Program walk-through:</h2>

<p align="center">

Scanned ports using Nmap:  <br/>
<img src="https://i.imgur.com/E6sPNPI.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Detailed review of ports using nmap -v (inet address of the targeted machine): <br/>
<img src="https://i.imgur.com/mZQtp82.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />

</p>
<h2>Conclusion of top 5 open ports and their associated vulnerabilities</h2>

        
     1. Port 21 - FTP
1.	FTP File transfer Protocol is used to send data across the network suing the 21 ports 
Some of the vulnerabilities are:
• FTP sends data like passwords and usernames which is the format of plain text and its vulnerable to mimt and smiffing attacks where hackers get access to the usernames and passwords using these techniques
•If the attackers get access to the FTP servers anonymously they can get access to sensitive datas and files or directories, resulting to data theft or manipulation. 
• FTP is also vulnerable to different attacks such as brute force attacks in this attack they try to attempt to guess valid usernames and passwords if the passwords are weak they get the access to the datas 
•	Vulnerability in FTP Servers: Older versions of FTP servers will have the known vulnerability which is good for attackers to gain unauthorised access and execute arbitrary code, or crash the service.
Mitigation:
•	Use SFTP (Secure FTP) or FTPS (FTP over SSL/TLS) can be used to secure.
•	Disable unauthorised and anonymous login and make strong authentication
•	Regular patch will be maintained.
________________________________________
2.	Port 514 - Shell (RSH or Remote Shell)

Port 514- shell (RSH or Remote shell)

•	Just like FTP, RSH sends sensitive data  like usernames and passwords in          plain sight,  This makes it easy for cybercriminals to eavesdrop and steal your   login details, also giving them access to your accounts.
•	Unauthenticated Access: RSH can be misconfigured to allow unauthenticated access from certain IP addresses. This can allow attackers to execute arbitrary commands on the target machine without requiring a valid username or password.
•	Privilege Escalation: If RSH is configured with weak access control or used with weak credentials, attackers may be able to execute commands as privileged users, potentially gaining root access to the system.
•	Vulnerable Implementations: Older versions of the RSH daemon may have security flaws that allow attackers to exploit them to gain remote access.
Mitigation strategy:
•	Replacing the RSH with SSH (Secure Shell), to encrypt data and gain more secure connection 
•	Usage of different mechanisms like authentication and access control which can help in restricting the system which can connect the RHS 
________________________________________
3. Port 513 - Login (rlogin)
rlogin is  a protocol which is an older version which provides  remote login capabilities to unix-based systems 
Associated Vulnerabilities:
•	Like FTP and RSH, rlogin transfers the data into plain text making it vulnerable and it will be easy for the attackers to get access by using a sniffing and MITM attacks 
•	As rlogin don’t have the feature of encrypt communication and protect sensitive data like passwords and usernames every commands are exposed and can be attacked at any time.
•	rlogin always relies on the trusted hosts, like one system trust the another one to allow the logins without the passwords if an attacker tries to prove that his system is trusted it allows him to get the access to the systems 
•	different implementations of rlogin contains different vulnerability that is exploited by the attackers to get access and change commands on the systems
   <h2>Mitigation:</h2>
•	Replace rlogin with SSH for securing the authentication process.
•	Ensure correct and steady authentication so that no one can enter the system and datas without correct permission________________________________________
4. Port 80  Hypertext Transfer Protocols
Service: HTTP is one of the main  protocol which is  used in  web pages.
Associated Vulnerabilities:
•	Web applications which is  running on port 80 may be vulnerable to SQL injection attacks isql quries in the backend and steal datas 
•	If the web application doesn’t check if the data input is not correct than it will be attacked using the XXS attacks where they inject different java scrips where this lead to shutting down of webpages and also hijacking , data steal, and also lead uisers to unwanted.
•	 (CSRF): CSRF is the process where it makes the user to buy and do unwanted actions in the website without their permission such as changing account details or making purchases.
•	Non accurate and not fully  configured web servers sometimes open redirects, attackers make url which redirect users to go to unwanted sites
•	 Web servers running outdated versions of software (like Apache or Nginx)will have vulnerability which will be exploited by attackers to gain unauthorised access 
   <h2>Mitigation:</h2>
•	We should be regularly updating the webservers patches and applications 
•	We should Implement input validation and sanitization to prevent SQL injection, XSS, and other web-based attacks.
•	Use HTTPS to protect data when transfering.
•	Employ Web Application Firewalls (WAFs) to detect and block common web vulnerabilities.
________________________________________
 

5. Port 2049 - NFS (Network File System)
NFS is used to share data across the network this nis mainly a protocol 
Associated Vulnerabilities:
•	NFS gives access  to any of the files to the host without the authentication process this lead to risk and this leads to stealing of data.
•	If the NFS is not configured correctly it leads to the unauthorised access to sensitive datas and files 
•	Denial of Service (DoS): NFS is prone to the  DoS attacks in this attack the attackers give large amount of request to the system which cracks the system  
•	Information Disclosure: if its not properly configured then the files and directories will be accessed it it contain any of the sensitive information like username and passwords it will help them gain access   
•	Man in the middle attacks also will be there
<h2>Mitigation:</h2>
•	We need to give access to trusted IP addresses or networks only.
•	Use NFSv4 with Kerberos authentication for encryption and communication
•	Ensure that exported directories  ________________________________________
<h2>Conclusion:</h2>
Top 5 open ports and the associated vulnerabilities
1. FTP port 21 is prone to the attacks which may occur such as plaintext transfrees also anonymous logins will be there so we can use the SFTP OR FTPS to protecxt from these types of errors  
2. Port 514 - RSH is having risks like  cleartext authentication and privilege escalation. Use SSH to prevent from occurring the risks. 
3. Port 513 - Login (rlogin) is at risk due to the  cleartext authentication and trust attacks. Use SSH to mitigate this. 
4. HTTP: Port 80 is having the risk of sql injection attacks and also web applicatioin attacks we can sole this by using the techniques like patching, and HTTPS. 
5. NFS port 2049 is having unauthenticated access risks , privilege escalation, and denial of service attacks to solve these risks we need to  restrict access and use NFSv4 with Kerberos

 .
<br />
<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
