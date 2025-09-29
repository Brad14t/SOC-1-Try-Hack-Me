# Incident-handling-with-Splunk
Try Hack Me Incident handling with Splunk

# Exploitation Phase

**1. What was the URI which got multiple brute force attempts?**

`/joomla/administrator/index.php`

<img width="1772" height="167" alt="Screenshot 2025-09-29 085326" src="https://github.com/user-attachments/assets/13c96e49-28e3-4257-8de4-a4454b41a067" />

**2. Against which username was the brute force attempt made?**

`admin`

<img width="801" height="182" alt="Screenshot 2025-09-29 085538" src="https://github.com/user-attachments/assets/107418c1-5b16-4548-93d5-ccc6d82bb57c" />

**3. What was the correct password for admin access to the content management system running imreallynotbatman.com?**

`batman`

<img width="775" height="127" alt="Screenshot 2025-09-29 085829" src="https://github.com/user-attachments/assets/7359d072-78a3-4772-b41d-26d0d17b169e" />

**4. How many unique passwords were attempted in the brute force attempt?**

`412`

<img width="863" height="450" alt="Screenshot 2025-09-29 090003" src="https://github.com/user-attachments/assets/78c4f602-f9b7-4e69-8db7-c2635036f608" />

**5. What IP address is likely attempting a brute force password attack against imreallynotbatman.com?**

`23.22.63.114` we know this because of all the attempts using different creds from this IP.

<img width="775" height="256" alt="Screenshot 2025-09-29 090114" src="https://github.com/user-attachments/assets/487b819e-d229-407d-aec2-69b41556e31b" />

**6. After finding the correct password, which IP did the attacker use to log in to the admin panel?**

`40.80.148.42` This was the successful login attempt.

<img width="1564" height="67" alt="Screenshot 2025-09-29 090343" src="https://github.com/user-attachments/assets/d85937e8-a223-41c3-a361-1d9a61eb4227" />

# Installation Phase

**7. Sysmon also collects the Hash value of the processes being created. What is the MD5 HASH of the program 3791.exe?**

First I use command `index=botsv1 "3791.exe" sourcetype="XmlWinEventLog" EventCode=1`

Then I scroll down to the packet that executed the .exe, and found the MD5 there. `AAE3F5A29935E6ABCC2C2754D12A9AF0`

<img width="1494" height="508" alt="Screenshot 2025-09-29 092434" src="https://github.com/user-attachments/assets/b56a2507-5f6f-484b-b111-d412940b9dd1" />

**8. Looking at the logs, which user executed the program 3791.exe on the server?**

I can find this with the last answer. 

`NT AUTHORITY\IUSR` is a red flag as an analyst. This is showing the file was executed via a web server's anonymous user account.

<img width="748" height="199" alt="Screenshot 2025-09-29 092655" src="https://github.com/user-attachments/assets/5292cba9-fa3a-495e-aed4-f41b5b556ebc" />

**9. Search hash on the virustotal. What other name is associated with this file 3791.exe?**

Entering in the MD5 hash into Virus Total, I can go to the details and see other names of this file.

<img width="986" height="319" alt="Screenshot 2025-09-29 093902" src="https://github.com/user-attachments/assets/bb53d65b-9ed3-47f7-b1ae-bd71327ec716" />

# Action on Objective

**10. What is the name of the file that defaced the imreallynotbatman.com website ?**

Using this query `index=botsv1 url="/poisonivy-is-coming-for-you-batman.jpeg" dest_ip="192.168.250.70" | table _time src dest_ip http.hostname url`

I can find the answer under url

<img width="1910" height="423" alt="Screenshot 2025-09-29 095049" src="https://github.com/user-attachments/assets/79f506e3-0f01-43d8-96fe-f6a78f90af49" />

**11. Fortigate Firewall 'fortigate_utm' detected SQL attempt from the attacker's IP 40.80.148.42. What is the name of the rule that was triggered during the SQL Injection attempt?**

I started with a few different queries, but the one that worked for me was `index=botsv1 src=40.80.148.42 sourcetype=fortigate_utm`

Then looking through the fields, there is one labled `Attack` this has the SQL rule there.

<img width="1307" height="540" alt="Screenshot 2025-09-29 100053" src="https://github.com/user-attachments/assets/b60c64bf-1942-400b-814a-2a4aa869ce0f" />

# Command and Control

**12. This attack used dynamic DNS to resolve to the malicious IP. What fully qualified domain name (FQDN) is associated with this attack?**

`prankglassinebracket.jumpingcrab.com`

I can find this with this query `index=botsv1 sourcetype=fortigate_utm"poisonivy-is-coming-for-you-batman.jpeg"`

Then looking at the field `url`

<img width="1402" height="459" alt="Screenshot 2025-09-29 101252" src="https://github.com/user-attachments/assets/10aab875-8843-42ca-aa1d-752a7a8543bb" />

# Weaponization

**13. What IP address has P01s0n1vy tied to domains that are pre-staged to attack Wayne Enterprises?**

<img width="1285" height="442" alt="Screenshot 2025-09-29 102212" src="https://github.com/user-attachments/assets/e6f61d31-8e2f-46d6-8f26-f5ac1b28e178" />

**14. Based on the data gathered from this attack and common open-source intelligence sources for domain names, what is the email address that is most likely associated with the P01s0n1vy APT group?**

I wasnt able to find this on my own, I used the hint given. The website didnt load for me, I would have to come back and check on a different network.

But to find the answer go to the link in the hint, it takes you to AlienVault, then enter is the domain `www.po1s0n1vy.com`

`lillian.rose@po1s0n1vy.com`

# Delivery

**15. What is the HASH of the Malware associated with the APT group?**

<img width="1304" height="640" alt="Screenshot 2025-09-29 104721" src="https://github.com/user-attachments/assets/d75e3683-003f-4d3b-b98c-980d17713d35" />

**16. What is the name of the Malware associated with the Poison Ivy Infrastructure?**

`MirandaTateScreensaver.scr.exe`

I can see this in the last screenshot

<img width="1231" height="441" alt="Screenshot 2025-09-29 104857" src="https://github.com/user-attachments/assets/2c1f2b31-d8b8-4a47-be0f-5b47767f99bf" />













