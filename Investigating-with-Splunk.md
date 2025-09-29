# Investigating-with-Splunk
Try Hack Me Investigating with Splunk


**1. How many events were collected and Ingested in the index main?**

I start with quering the index with `index=main` then I can see how many entries.

<img width="774" height="206" alt="Screenshot 2025-09-29 130803" src="https://github.com/user-attachments/assets/2029c929-acbf-48ed-8774-f4c28ff09de5" />

**2. On one of the infected hosts, the adversary was successful in creating a backdoor user. What is the new username?**

First we need the Event ID associated with account creation, that is `4720`

So my query looks like `index=main EventID=4720` then in the details I can find the answer of the new account.

`A1berto`

<img width="897" height="344" alt="Screenshot 2025-09-29 131945" src="https://github.com/user-attachments/assets/125d0bea-8454-46a4-8bbb-a294d6c981e5" />

**3. On the same host, a registry key was also updated regarding the new backdoor user. What is the full path of that registry key?**

First I made a query of `index=main Hostname="Micheal.Beaven" EventID=12`

The hostname was found from the last answer, then event id 12 is creation of registry keys.

Once I did this, I selected the field `TargetObject` in there I see 1 for the user we are looking for. And thats the answer.

<img width="999" height="347" alt="Screenshot 2025-09-29 132959" src="https://github.com/user-attachments/assets/2527e247-b301-44fc-b14c-4d10bd77c723" />

**4. Examine the logs and identify the user that the adversary was trying to impersonate.**

This one required an eye to see. We know the new account is `A1berto`, but looking through the fields I selected `Users` and there we can see all traffic from the users, I dont see anything from malicous actor. But I do see `Alberto` this is common to just change 1 thing in the name to blend in.

<img width="667" height="241" alt="Screenshot 2025-09-29 135503" src="https://github.com/user-attachments/assets/46467930-d5b0-4e08-be25-d285dce4034e" />

<img width="915" height="484" alt="Screenshot 2025-09-29 135513" src="https://github.com/user-attachments/assets/1236e42d-036e-41ce-8bdb-897e2571fd13" />

**5. What is the command used to add a backdoor user from a remote computer?**

`C:\windows\System32\Wbem\WMIC.exe" /node:WORKSTATION6 process call create "net user /add A1berto paw0rd1`

To start I queried with `index=main "A1berto"` then went through the entries and came across one with the answer in the command line section.

<img width="1471" height="267" alt="Screenshot 2025-09-29 140611" src="https://github.com/user-attachments/assets/2106ee83-a68c-4c22-b552-251a172e6e6b" />

**6. How many times was the login attempt from the backdoor user observed during the investigation?**

To find the answer use `index=main User=A1berto`

<img width="689" height="186" alt="Screenshot 2025-09-29 140827" src="https://github.com/user-attachments/assets/375d1f3c-2dd0-4d16-a2ca-b648d7567f5a" />

**7. What is the name of the infected host on which suspicious Powershell commands were executed?**

In the same entrie as number 5, we can use the hostname as the answer.

<img width="640" height="259" alt="Screenshot 2025-09-29 141042" src="https://github.com/user-attachments/assets/35e10840-2b11-4708-9058-933d9b3993fa" />

**8. PowerShell logging is enabled on this device. How many events were logged for the malicious PowerShell execution?**

I use the query `index=main Microsoft-Windows-PowerShell/Operational` these will be all powershell specific logs.

<img width="725" height="185" alt="Screenshot 2025-09-29 141359" src="https://github.com/user-attachments/assets/79146637-500d-4a34-9657-7735022e8ea0" />

**9. An encoded Powershell script from the infected host initiated a web request. What is the full URL?**

Using `index=main Microsoft-Windows-PowerShell/Operational` the first entry I find the powershell, then I put into Cyber chef and decoded the text to 

Then defang the output to `hxxp[://]10[.]10[.]10[.]5/news[.]php`

<img width="1165" height="426" alt="Screenshot 2025-09-29 142538" src="https://github.com/user-attachments/assets/804aa8fa-6e68-4ba6-aa0a-e6919a37bf18" />








