# THM-Sysmon & OSQuery
This will be my process and explanation of the Try Hack Me Sysmon modules.

**1. How many event ID 3 events are in C:\Users\THM-Analyst\Desktop\Scenarios\Practice\Filtering.evtx?**

I editted a command given and landed on this `Get-WinEvent -Path C:\Users\THM-Analyst\Desktop\Scenarios\Practice\Filtering.evtx -FilterXPath '*/System/EventID=3' | Measure-Object`

<img width="1059" height="235" alt="Screenshot 2025-09-18 131034" src="https://github.com/user-attachments/assets/4f17608c-e191-43f9-b5b9-c67c47ffa854" />

**2. What is the UTC time of the first network event in the same logfile? Note that UTC time is shown only in the "Details" tab.**

For this I used the GUI within Event Viewer. And just sorted by time, clicked the first entry and the UTC time is displayed.

<img width="722" height="645" alt="Screenshot 2025-09-18 131401" src="https://github.com/user-attachments/assets/8f6322b8-b7fd-4286-aacd-3aa3bbf8989c" />

**3. What is the full registry key of the USB device calling svchost.exe in Investigation 1?**

First I go through the entries and see the event when the usb was inserted then going to the 2 entries after that I can see the registry key that was used.

`HKLM\System\CurrentControlSet\Enum\WpdBusEnumRoot\UMB\2&37c186b&0&STORAGE#VOLUME#_??_USBSTOR#DISK&VEN_SANDISK&PROD_U3_CRUZER_MICRO&REV_8.01#4054910EF19005B3&0#\FriendlyName`

<img width="881" height="302" alt="Screenshot 2025-09-18 132716" src="https://github.com/user-attachments/assets/97f62e5f-0855-4de7-b65d-f67d4849e88e" />

**4. What is the device name when being called by RawAccessRead in Investigation 1?**

For this I go to the first RawAccessRead entry and can find the answer by going through the details.

<img width="813" height="542" alt="Screenshot 2025-09-18 133021" src="https://github.com/user-attachments/assets/78f58169-ce2f-4f83-93e5-65ef94435611" />

**5. What is the first exe the process executes in Investigation 1?**

First I tried going to the first packet after the RawAccessRead entries and found the exe file there.

<img width="355" height="108" alt="Screenshot 2025-09-18 134809" src="https://github.com/user-attachments/assets/d87c0e65-42dd-4624-974f-5b48237b2f8a" />

<img width="433" height="274" alt="Screenshot 2025-09-18 134834" src="https://github.com/user-attachments/assets/c3058319-7afb-489f-8f15-28d6e18ee420" />

**6. What is the full path of the payload in Investigation 2?**

First I go to the 3rd entrie since that is the process creation. And I can find the full path in the details tab.

<img width="863" height="343" alt="Screenshot 2025-09-18 135805" src="https://github.com/user-attachments/assets/d5559db0-23da-4da6-9147-3dd8a6977d68" />

**7. What is the full path of the file the payload masked itself as in Investigation 2?**

Looking through the details, I found a parent command line, this is what I am looking for.

<img width="739" height="491" alt="Screenshot 2025-09-18 140201" src="https://github.com/user-attachments/assets/c1846b33-9aa4-414c-8e8c-aa5ae2127a26" />

**8. What signed binary executed the payload in Investigation 2?**

You can find this right before the full path of the payload.

<img width="825" height="391" alt="Screenshot 2025-09-18 140655" src="https://github.com/user-attachments/assets/5e4b018d-18dc-42b2-95f1-e61e283e10b3" />

**9. What is the IP of the adversary in Investigation 2?**

First I will go to the Network connection detected packet, then go to the details and find the destination IP.

<img width="554" height="575" alt="Screenshot 2025-09-18 141014" src="https://github.com/user-attachments/assets/0ef5845b-6069-4a6b-aafa-245d8c7bfac9" />

**10. What back connect port is used in Investigation 2?**

For this I can use the same packet and look for destination port.

<img width="517" height="565" alt="Screenshot 2025-09-18 141052" src="https://github.com/user-attachments/assets/601cbf5a-d042-4f4f-b248-b2cb6dd69f42" />

**11. What is the IP of the suspected adversary in Investigation 3.1?**

Opening the first Network Cennection packet, I can see the destination Ip in the details tab.

<img width="640" height="452" alt="Screenshot 2025-09-18 142417" src="https://github.com/user-attachments/assets/f6314b82-3914-4ad2-962a-806740e4e85a" />

**12. What is the hostname of the affected endpoint in Investigation 3.1?**

I can find the answer in the same tab, looking for source host name.

<img width="686" height="314" alt="Screenshot 2025-09-18 142452" src="https://github.com/user-attachments/assets/2f376b13-d283-4721-a6cf-bdeacf9daf3b" />

**13. What is the hostname of the C2 server connecting to the endpoint in Investigation 3.1?**

Same tab

<img width="676" height="412" alt="Screenshot 2025-09-18 142601" src="https://github.com/user-attachments/assets/2035c136-4819-43cc-b81f-3b773a71cb05" />

**14. Where in the registry was the payload stored in Investigation 3.1?**

Looking through the entries, I landed on a Registry Value Set packet and looking at the details I can find the location.

<img width="373" height="204" alt="Screenshot 2025-09-18 143050" src="https://github.com/user-attachments/assets/a7525eab-d535-44e8-9cd4-0e57ac4b5cbf" />

<img width="932" height="635" alt="Screenshot 2025-09-18 142957" src="https://github.com/user-attachments/assets/1546e776-ff4d-4636-8cd8-be21c16c30da" />

**15. What PowerShell launch code was used to launch the payload in Investigation 3.1?**

I go to the first Event ID 13 entry since their is a powershell command within it.

<img width="944" height="643" alt="Screenshot 2025-09-18 143732" src="https://github.com/user-attachments/assets/4cd0b5ef-ff8b-4d5e-8f21-d704e8eaa0ac" />

**16. What is the IP of the adversary in Investigation 3.2?**

First I sort by time and go to the earliest entry, it is a Network Connection detected, so thats perferct. I go into the deatials and find the destination IP.

<img width="679" height="541" alt="Screenshot 2025-09-18 144037" src="https://github.com/user-attachments/assets/2e99c5e2-506f-4fcd-8dde-6e39effaab2f" />

**17. What is the full path of the payload location in Investigation 3.2?**

First I go to the earliest Process Created entry. Selected that and go to the details, there I can find the path along with the command performed.

<img width="876" height="590" alt="Screenshot 2025-09-18 144302" src="https://github.com/user-attachments/assets/196f0561-b469-43a9-8de8-1f9db99b2e72" />

**18. What was the full command used to create the scheduled task in Investigation 3.2?**

Looking through the entries I was focusing on Process Created packets. The 1st earliest event ID 1 is a normal process, but going to the 2nd entry I can see the same user as before, performing a command.

<img width="871" height="541" alt="Screenshot 2025-09-18 145052" src="https://github.com/user-attachments/assets/960a37b1-79fa-4bc1-bcc7-20f70eafd189" />

**19. What process was accessed by schtasks.exe that would be considered suspicious behavior in Investigation 3.2?**

Going through the packets, I came accross Event ID 10, and in there I can see source image and target image. The source is schtasks.exe and the target is lsass.exe

<img width="465" height="301" alt="Screenshot 2025-09-18 145815" src="https://github.com/user-attachments/assets/39dd1d0b-b549-431f-8779-2031841370c2" />

**20. What is the IP of the adversary in Investigation 4?**

Going into the first Network Connection packet, I can find the destination IP.

<img width="790" height="539" alt="Screenshot 2025-09-18 150028" src="https://github.com/user-attachments/assets/04438b05-1f0e-4efc-87ea-11a765fc315d" />

**21. What port is the adversary operating on in Investigation 4?**

I can find this right below the last answer.

**22. What C2 is the adversary utilizing in Investigation 4?**

Right below the last answer.

<img width="763" height="434" alt="Screenshot 2025-09-18 150156" src="https://github.com/user-attachments/assets/baf2e159-8f6b-4e47-9431-58e586ca8782" />

# OSQuery 

**1. How many tables are returned when we query "table process" in the interactive mode of Osquery?**

Start osquery in interactive mode by using `osqueryi`

Then `.table process`

<img width="641" height="164" alt="Screenshot 2025-09-19 093148" src="https://github.com/user-attachments/assets/8e08a931-bdcf-4a67-a64a-3ff9ef1c9e0d" />

**2. Looking at the schema of the processes table, which column displays the process id for the particular process?**

`.schema process` this will display the pid, which we know as Process ID.

<img width="1052" height="419" alt="Screenshot 2025-09-19 093531" src="https://github.com/user-attachments/assets/2dd616e0-4a14-4075-bab7-e7f354fa0904" />

**3. Examine the .help command, how many output display modes are available for the .mode command?**

I use the command `.help` then I can see there are 5 display modes.

<img width="745" height="136" alt="Screenshot 2025-09-19 093620" src="https://github.com/user-attachments/assets/21397ac6-d5b7-469a-9a12-6dd2a8094f71" />

**4. In Osquery version 5.5.1, how many common tables are returned, when we select both Linux and Window Operating system?**

Go to this link https://osquery.io/schema/5.5.1/

Then select Windows and Linux.

<img width="666" height="214" alt="Screenshot 2025-09-19 093826" src="https://github.com/user-attachments/assets/a6a81f81-1118-4538-b46b-b60e4b091b43" />

**5. In Osquery version 5.5.1, how many tables for MAC OS are available?**

<img width="1118" height="371" alt="Screenshot 2025-09-19 093929" src="https://github.com/user-attachments/assets/819a3733-3fa7-49a2-8fb1-bbb260515343" />

**6. In the Windows Operating system, which table is used to display the installed programs?**

<img width="1657" height="328" alt="Screenshot 2025-09-19 094946" src="https://github.com/user-attachments/assets/57cff7fc-265b-4157-aac5-f8c1f04ec69a" />

**7. In Windows Operating system, which column contains the registry value within the registry table?**

<img width="727" height="334" alt="Screenshot 2025-09-19 095116" src="https://github.com/user-attachments/assets/907ad173-1f4e-4f65-a216-510f675ff6d8" />

**8. Using Osquery, how many programs are installed on this host?**

`SELECT COUNT(*) FROM programs;`

This is a basic SQL cquery, I am just counting the values from the programs file.

<img width="616" height="231" alt="Screenshot 2025-09-19 095444" src="https://github.com/user-attachments/assets/64ba6572-4a5d-4e2c-aa84-488a65f39a36" />

**9. Using Osquery, what is the description for the user James?**

`SELECT description FROM users WHERE user = 'James'`

Another basic query where I am selecting the description value, from the users table, and only looking for a user value of James.

<img width="718" height="189" alt="Screenshot 2025-09-19 095702" src="https://github.com/user-attachments/assets/74943fa0-f95a-4980-9bf2-e4ccd6d86e69" />

**10. When we run the following search query, what is the full SID of the user with RID '1009'? Query: select path, key, name from registry where key = 'HKEY_USERS';**

After running the query I can copy and paste the full SID

<img width="520" height="206" alt="Screenshot 2025-09-19 100056" src="https://github.com/user-attachments/assets/99cff724-c523-4883-8d42-647be91f7cff" />

**11. When we run the following search query, what is the Internet Explorer browser extension installed on this machine? Query: select * from ie_extensions;**

<img width="532" height="208" alt="Screenshot 2025-09-19 102449" src="https://github.com/user-attachments/assets/15ecc7e5-35c7-4455-8825-0ae1f37b5296" />

**12. After running the following query, what is the full name of the program returned? Query: select name,install_location from programs where name LIKE '%wireshark%';**

<img width="539" height="247" alt="Screenshot 2025-09-19 102656" src="https://github.com/user-attachments/assets/05fa7d8b-203c-4597-b117-44ac73b163f7" />

**13. Which table stores the evidence of process execution in Windows OS?**

Checking from the link provided earlier.

<img width="1243" height="540" alt="Screenshot 2025-09-19 103017" src="https://github.com/user-attachments/assets/d54a818f-ce04-4f5e-9703-7423593555be" />

**14. One of the users seems to have executed a program to remove traces from the disk; what is the name of that program?**

I started with the command `select * from userassist;` and went through the output and found `DiskWipe.exe`

<img width="1057" height="60" alt="Screenshot 2025-09-19 103847" src="https://github.com/user-attachments/assets/ac5335ed-9ddf-4cb0-859e-7eb831e127b2" />

**15. Create a search query to identify the VPN installed on this host. What is name of the software?**

I can find this answer right above the last answer.

<img width="904" height="126" alt="Screenshot 2025-09-19 104026" src="https://github.com/user-attachments/assets/8c30a3a6-6e32-4419-b4d6-b317e3ea3328" />

**16. How many services are running on this host?**

`select count(*) from services;`

<img width="447" height="171" alt="Screenshot 2025-09-19 104145" src="https://github.com/user-attachments/assets/5cf3e9dc-071f-493b-96eb-52329ffddc8c" />

**17. A table autoexec contains the list of executables that are automatically executed on the target machine. There seems to be a batch file that runs automatically. What is the name of that batch file (with the extension .bat)?**


`select path from autoexec where path like '%.bat'` 

<img width="1033" height="177" alt="Screenshot 2025-09-19 104921" src="https://github.com/user-attachments/assets/738f89a5-c23c-4f45-8fb1-b27b115eeb63" />


**18. What is the full path of the batch file found in the above question? (Last in the List)**

This answer is already showing from the last query.


<img width="1058" height="450" alt="Screenshot 2025-09-19 105036" src="https://github.com/user-attachments/assets/cf6fefe5-706f-41cb-a056-6a08b5b15b8a" />






















