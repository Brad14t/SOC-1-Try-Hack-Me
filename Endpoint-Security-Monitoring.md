# THM-Endpoint-Security-Monitoring
This will be my process through answering the Try Hack Me Endpoint Security Monitoring modules.

`54 Total questions`

**1. What is the normal parent process of services.exe?**

`wininit.exe`

**2. What is the name of the network utility tool introduced in this task?**

`tcpview`

**3. Where do the Windows Event logs (.evtx files) typically reside?**

`C:\Windows\System32\winevt\Logs\`

**4. Provide the command used to enter OSQuery CLI.**

`osqueryi`

**5. What does EDR mean? Provide the answer in lowercase.**

`endpoint detection and response`

**6. Provide the flag for the simulated investigation activity.**

For this I just went through and picked what I thought was malicous, and ended uo getting the flag `THM{3ndp01nt_s3cur1ty!}`


**7. What PID should System always be?**

`4`

<img width="663" height="50" alt="Screenshot 2025-09-08 140558" src="https://github.com/user-attachments/assets/763dfb44-32cc-45d5-a7da-4608207aaea3" />

**8. side from csrss.exe, what process does smss.exe spawn in Session 1?**

<img width="723" height="124" alt="Screenshot 2025-09-08 140856" src="https://github.com/user-attachments/assets/d3a800a6-270f-4bd2-a40d-c6de75658a47" />

**9. What was the process which had PID 384 and PID 488?**

`smss.exe`

<img width="635" height="90" alt="Screenshot 2025-09-08 141134" src="https://github.com/user-attachments/assets/f750e2f4-c53b-4ed2-aa7c-f47d739a9341" />

**10. Which process might you not see running if Credential Guard is not enabled?**

`lsaiso.exe`

<img width="696" height="118" alt="Screenshot 2025-09-08 141318" src="https://github.com/user-attachments/assets/dee95e3a-8201-49d0-9284-b1fcd4336757" />

**11. How many instances of services.exe should be running on a Windows system?**

`1` There should only ever be 1 instance.

**12. What single letter parameter should always be visible in the Command line or Binary path?**

`k`

<img width="666" height="123" alt="Screenshot 2025-09-08 141717" src="https://github.com/user-attachments/assets/30f34b0e-4403-4d74-8365-bddaac077c91" />

**13. What is the parent process for LSASS?**

<img width="681" height="373" alt="Screenshot 2025-09-08 141846" src="https://github.com/user-attachments/assets/49387684-fae7-4955-abd8-6452591335cc" />

**14. What is the non-existent parent process for winlogon.exe?**

<img width="731" height="113" alt="Screenshot 2025-09-08 141952" src="https://github.com/user-attachments/assets/29ebe607-a821-445e-818a-a0147c156e64" />

**15. What is the non-existent process for explorer.exe?**

<img width="714" height="169" alt="Screenshot 2025-09-08 142104" src="https://github.com/user-attachments/assets/968a6a64-2be4-4bb1-bc8e-59f2cb71f632" />

<img width="1133" height="456" alt="Screenshot 2025-09-08 142126" src="https://github.com/user-attachments/assets/7e5c69cf-c1a3-433a-bae2-052653094a68" />

# Sysinternals

**16. When did Microsoft acquire the Sysinternals tools?**

`2006`

<img width="659" height="143" alt="Screenshot 2025-09-09 134016" src="https://github.com/user-attachments/assets/0b77fa14-e7f2-40e8-ace7-f8796c9a860a" />

**17. What is the last tool listed within the Sysinternals Suite?**

`Zoomit`

<img width="943" height="710" alt="Screenshot 2025-09-09 134441" src="https://github.com/user-attachments/assets/b7084b6d-a5bb-4ff7-9642-0e4c17da01bd" />

**18. What service needs to be enabled on the local host to interact with live.sysinternals.com?**

`webclient`

<img width="689" height="235" alt="Screenshot 2025-09-09 134741" src="https://github.com/user-attachments/assets/5f3b2436-ce13-4b6c-85f6-240ec5fa9425" />

**19. There is a txt file on the desktop named file.txt. Using one of the three discussed tools in this task, what is the text within the ADS?**

First I use 1 of the utlities that was provided `streams file.txt`

Then `./file.txt:ads.txt`

<img width="616" height="400" alt="Screenshot 2025-09-09 135658" src="https://github.com/user-attachments/assets/7901cbdb-6adb-4b07-b1e0-1a58d97d9b39" />

<img width="294" height="138" alt="Screenshot 2025-09-09 135650" src="https://github.com/user-attachments/assets/00525b76-4c48-4f53-a283-66d7e0392659" />

**20. Using WHOIS tools, what is the ISP/Organization for the remote address in the screenshots above?**

`Microsoft Corporation`

<img width="683" height="128" alt="Screenshot 2025-09-09 142430" src="https://github.com/user-attachments/assets/16375bb1-2e3e-43ac-a5a8-7a95c03eb844" />

<img width="565" height="351" alt="Screenshot 2025-09-09 142414" src="https://github.com/user-attachments/assets/71d9ad99-ae81-4bb1-81e6-4a5bf350a350" />

**21. What entry was updated?**

First I run `autoruns`

Then I see which entry was updated.

<img width="368" height="90" alt="Screenshot 2025-09-09 143152" src="https://github.com/user-attachments/assets/6c3ce4d6-81b5-45b5-ba44-bd35bd2009e6" />

**22. What is the updated value?**

<img width="282" height="300" alt="Screenshot 2025-09-09 144303" src="https://github.com/user-attachments/assets/dae98fc9-5c43-4881-ac37-4728ef37a733" />

**23. Run the Strings tool on ZoomIt.exe. What is the full path to the .pdb file?**

`strings ZoomIt.exe`

Then `.\ZoomIt.exe | findstr /i .pdb`

<img width="851" height="451" alt="Screenshot 2025-09-09 145143" src="https://github.com/user-attachments/assets/d1e2d497-fed1-4b5b-8afc-a0e9af90f1d5" />

# Windows Event Logs

**24. What is the Event ID for the earliest recorded event?**

First I go to the folder location given. Then sort from latest to earliest.

<img width="1193" height="172" alt="Screenshot 2025-09-15 115302" src="https://github.com/user-attachments/assets/a3469e10-0990-42e2-864b-9a1af9bcd7b9" />

**25. Filter on Event ID 4104. What was the 2nd command executed in the PowerShell session?**

First I set a filter.

<img width="815" height="823" alt="Screenshot 2025-09-15 115350" src="https://github.com/user-attachments/assets/9397576a-46a9-424f-99b7-9841c6911883" />

Go to the second entry.

![1_oxpEgeLgRENDjezrANr1PQ](https://github.com/user-attachments/assets/13e8af19-2328-4ea4-9ed4-087ec80fe029)

**26. What is the Task Category for Event ID 4104?**

Answer provided from same screen.

<img width="891" height="477" alt="Screenshot 2025-09-15 120125" src="https://github.com/user-attachments/assets/7d558722-abc3-46c3-ba19-2c1a8cfeb5b0" />

**27. Analyze the Windows PowerShell log. What is the Task Category for Event ID 800?**

First I head to the new location of the files. Go to Windows Powershell under OpenSSH.

<img width="286" height="108" alt="Screenshot 2025-09-15 120325" src="https://github.com/user-attachments/assets/325058f3-cde3-4f20-a2f2-ca4f964b19f8" />

Then filter EventID 800

<img width="805" height="826" alt="Screenshot 2025-09-15 120438" src="https://github.com/user-attachments/assets/7672c447-e974-4550-b7e0-22c2cdd3a8b2" />

Then I can find the answer looking at an entry.

<img width="837" height="481" alt="Screenshot 2025-09-15 120550" src="https://github.com/user-attachments/assets/c164a45e-55ed-4006-a873-d786016bf7f9" />

**28. How many log names are in the machine?**

`wevtutil el | Measure-Objects`

el supplies all log names, and Measure Objects just counts the total. For some reason my answer was 1 less than the output.

<img width="654" height="257" alt="Screenshot 2025-09-15 121007" src="https://github.com/user-attachments/assets/80239c16-27e4-4e3b-90c2-ff4c066bda92" />

**29. What event files would be read when using the query-events command?**

<img width="945" height="102" alt="Screenshot 2025-09-15 121311" src="https://github.com/user-attachments/assets/97e3c0df-4950-40ad-99d4-481cedefeabb" />

**30. What option would you use to provide a path to a log file?**

Looking through the options I foud the answer by using `wevtutil qe /?`

<img width="860" height="450" alt="Screenshot 2025-09-15 122056" src="https://github.com/user-attachments/assets/c49b6e26-72c6-4c96-86c7-1695aa58fe12" />

**31. What is the VALUE for /q?**

From that same search I can find the answer with the output.

<img width="897" height="102" alt="Screenshot 2025-09-15 122216" src="https://github.com/user-attachments/assets/2db25430-3f8d-404e-885d-5feaeb27c104" />

**32. What is the log name?**

<img width="372" height="107" alt="Screenshot 2025-09-15 122503" src="https://github.com/user-attachments/assets/727f3aab-1edc-4715-a213-11fd26f28694" />

**33. What is the /rd option for?**

I can find the answer from the output of 30.

<img width="831" height="65" alt="Screenshot 2025-09-15 122604" src="https://github.com/user-attachments/assets/197c1c4c-c31d-4f05-b300-4ab096ecd3d6" />

**34. What is the /c option for?**

Same thing I can get output from 30.

<img width="382" height="63" alt="Screenshot 2025-09-15 122717" src="https://github.com/user-attachments/assets/f6559ec8-add3-4a58-8b25-310ca5d3cf4f" />

**35. Execute the command from Example 1 (as is). What are the names of the logs related to OpenSSH?**

`Get-WinEvent -ListLog *`

Then scroll down to find entries with Open SSH.

<img width="676" height="54" alt="Screenshot 2025-09-15 124045" src="https://github.com/user-attachments/assets/67a03d5e-8554-4834-bed4-2ff0f6e53973" />

**36. Execute the command from Example 8. Instead of the string *Policy* search for *PowerShell*. What is the name of the 3rd log provider?**

`Get-WinEvent -ListProvider *PowerShell*`

And its the 3rd name.

<img width="1061" height="525" alt="Screenshot 2025-09-15 124333" src="https://github.com/user-attachments/assets/65061641-1bde-464b-86e6-8438eddfc82b" />

**37. Execute the command from Example 9. Use Microsoft-Windows-PowerShell as the log provider. How many event ids are displayed for this event provider?**

`(Get-WinEvent -ListProvider Microsoft-Windows-PowerShell).Events | Format-Table Id, Description | Measure-Object`

<img width="1277" height="242" alt="Screenshot 2025-09-15 124708" src="https://github.com/user-attachments/assets/47751d10-b5ec-4061-86a8-78f6202e6ceb" />

**38. How do you specify the number of events to display?**

Looking at the site provided I was able to find this.

<img width="849" height="139" alt="Screenshot 2025-09-15 124813" src="https://github.com/user-attachments/assets/fc896bd7-1612-4d6a-b11c-b2ddc2c86694" />

`-MaxEvents`

**39. When using the FilterHashtable parameter and filtering by level, what is the value for Informational?**

After doing some research I found this site and scrolled down to find the answer.

https://learn.microsoft.com/en-us/powershell/scripting/samples/creating-get-winevent-queries-with-filterhashtable?view=powershell-7.5&viewFallbackFrom=powershell-7.3

<img width="889" height="415" alt="Screenshot 2025-09-15 124949" src="https://github.com/user-attachments/assets/08495991-256e-4b57-b824-1a48375ac663" />

**40. Using the knowledge gained on Get-WinEvent and XPath, what is the query to find WLMS events with a System Time of 2020-12-15T01:09:08.940277500Z?**

To start answering this question I had to break down each part of the query and see what each part does.

I start with needing to use the Application event logs `Get-WinEvent -LogName Application`

Next I need the XPath query to filter `-FilterXPath`

Then I just want the system provider name that matches WLMS `'*/System/Provider[@Name="WLMS"]`

Then I just need to match the time that was given `and */System/TimeCreated[@SystemTime="2020-12-15T01:09:08.940277500Z"]'`

Full query:

`Get-WinEvent -LogName Application -FilterXPath '*/System/Provider[@Name="WLMS"] and */System/TimeCreated[@SystemTime="2020-12-15T01:09:08.940277500Z"]'`

**41. Using Get-WinEvent and XPath, what is the query to find a user named Sam with an Logon Event ID of 4720?**

After some trial and error, I used one of the queries provided and adjusted.

`Get-WinEvent -LogName Security -FilterXPath '*/EventData/Data[@Name="TargetUserName"]="Sam" and */System/EventID=4720'`

**42. Based on the previous query, how many results are returned?**

Based on the last one, I can see there are 2 entries.

<img width="1082" height="294" alt="Screenshot 2025-09-18 110407" src="https://github.com/user-attachments/assets/ddacf885-a4b0-4dd7-b136-ef2c54145e0c" />

**43. Based on the output from the question #2, what is Message?**

Just copy and paste the message from the query.

**44. Still working with Sam as the user, what time was Event ID 4724 recorded? (MM/DD/YYYY H:MM:SS [AM/PM])**

I can just change the query from before changing just the EventID from 4720 to 4724

<img width="1054" height="234" alt="Screenshot 2025-09-18 111028" src="https://github.com/user-attachments/assets/17ac9f28-0af0-4d64-b383-15c01dbec575" />

**45. What is the Provider Name?**

We can see this from the output from the lst question.

**46. What event ID is to detect a PowerShell downgrade attack?**

How you can tell if there is a powershell downgrade, you can filter event ID for 400, then look at the `Engine Version` if below 5.0 shows sighn of downgrade attack.

<img width="543" height="289" alt="Screenshot 2025-09-18 112730" src="https://github.com/user-attachments/assets/16d12b59-6e5f-4678-be99-339b8e8de0d1" />

**47. What is the Date and Time this attack took place? (MM/DD/YYYY H:MM:SS [AM/PM])**

Looking through Event ID 400 entries, I can see the first one is the attack because I can compair the Engine Version. I will provide an example of one of the other entries and what it should look like.

<img width="812" height="298" alt="Screenshot 2025-09-18 113058" src="https://github.com/user-attachments/assets/1d426f63-9819-4339-9377-c36a96509e48" />

**48. A Log clear event was recorded. What is the 'Event Record ID'?**

Doing some research I found its suggested to start with Event ID 1102, but there is no set ID for log clears. But after going through a couple ID's I found 1 entry for Event ID `104` and read the description saying it was the log clear entry.

<img width="944" height="636" alt="Screenshot 2025-09-18 113535" src="https://github.com/user-attachments/assets/ee2bffdb-cb21-45d8-a742-c593847f3573" />

<img width="464" height="316" alt="Screenshot 2025-09-18 113754" src="https://github.com/user-attachments/assets/b28b4659-21be-4bb2-8ee1-8ce7a75e723a" />

**49. What is the name of the computer?**

Scrolling through the details I can find this.

<img width="649" height="489" alt="Screenshot 2025-09-18 113931" src="https://github.com/user-attachments/assets/a60b405a-0bb3-4a9d-a627-5b6fc3148503" />

**50. What is the name of the first variable within the PowerShell command?**

So after reading the hint, I tried CML query. But that didnt work so I looked up the Event ID for raw Powershell script and found `4104` then I filtered to that ID. Then just went to the oldest entry and found the answer within ther details.

**51. What is the Date and Time this attack took place? (MM/DD/YYYY H:MM:SS [AM/PM])**

We can find this answer in the same page.

<img width="767" height="360" alt="Screenshot 2025-09-18 115151" src="https://github.com/user-attachments/assets/8274ba02-2c77-4257-a3dd-2d3a0ee73758" />

**52. What is the Execution Process ID?**

To see this I used the XML tab.

<img width="771" height="389" alt="Screenshot 2025-09-18 115338" src="https://github.com/user-attachments/assets/354f491d-3b39-4cbd-b1bb-5393737594be" />

**53. What is the Group Security ID of the group she enumerated?**

First I need an event ID, I researched that `4799` checks which user is in which group. So I filtered that, then clicked the first entry and looked for TargetSid value.

<img width="602" height="398" alt="Screenshot 2025-09-18 115746" src="https://github.com/user-attachments/assets/5b2fb82a-76c6-4604-8edc-0138a9d667ff" />

**54. What is the event ID?**

Like I said the Event ID was `4799`

<img width="1024" height="444" alt="Screenshot 2025-09-18 120053" src="https://github.com/user-attachments/assets/07b96223-28b8-422b-9481-c39fa6ab4125" />

























