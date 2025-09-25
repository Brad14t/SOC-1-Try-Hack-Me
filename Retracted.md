# THM-Retracted

Investigate the case of the missing ransomware.

**1. What is the full path of the text file containing the "message"?**

I can see the message, labeled her name. First I righ click the file and go to properties, then go to details. There I can find the full path.

`C:\Users\Sophie\Desktop\SOPHIE.txt`

<img width="410" height="338" alt="Screenshot 2025-09-24 085605" src="https://github.com/user-attachments/assets/c4170074-0b11-45bd-b601-02e19291ba07" />

**2. What program was used to create the text file?**

I can see this by looking at propertie, and see notepad.exe is the application used. Look at last photo.

**3. What is the time of execution of the process that created the text file? Timezone UTC (Format YYYY-MM-DD hh:mm:ss)**

First I will start by going to `Event Viewer`, then going to `Applications and Services > Microsoft > Windows > Sysmon > Operatinal`

Then I filter event ID `1`, then select the `Find` option. Finally click the first one found and can find the answer there.

<img width="811" height="826" alt="Screenshot 2025-09-24 091525" src="https://github.com/user-attachments/assets/e53c0727-407e-412d-a6a5-1616ae84ddca" />

<img width="664" height="209" alt="Screenshot 2025-09-24 091751" src="https://github.com/user-attachments/assets/d6370187-7b86-46c9-8d1b-9ba45940a7d8" />

<img width="858" height="307" alt="Screenshot 2025-09-24 091854" src="https://github.com/user-attachments/assets/037a2383-56af-4e2f-a4d7-29e1ef5890a9" />

**4. What is the filename of this "installer"? (Including the file extension)**

First I checked out internet explorer, and looked at the downloads. But nothing.

Then I opened Edge, and selected downloads and found the answer there.

<img width="1768" height="628" alt="Screenshot 2025-09-25 105158" src="https://github.com/user-attachments/assets/142a324b-de1e-4144-862e-9461b7485f08" />

**5. What is the download location of this installer?**

I'll first open the location of the file, then go to security to get full path.

<img width="415" height="399" alt="Screenshot 2025-09-25 105457" src="https://github.com/user-attachments/assets/023b657a-9722-4f01-af01-bf603cfe0885" />

<img width="546" height="330" alt="Screenshot 2025-09-25 105517" src="https://github.com/user-attachments/assets/feebbb1e-fc25-4979-83e8-580d90d34b9e" />

**6. The installer encrypts files and then adds a file extension to the end of the file name. What is this file extension?**

First I will go into `Event Viewer` the  filter for `Event ID 11` since this is centered around file creation. Then I `Find` `antivirus.exe`, select the first entry found then I can see the answer there with Target file. `dmp`

<img width="948" height="665" alt="Screenshot 2025-09-25 110052" src="https://github.com/user-attachments/assets/eb9db178-ca34-40f3-bbd7-b2659b9b7aa8" />

**7. The installer reached out to an IP. What is this IP?**

To start I will filter by `Event ID 3` since that indicates a new network connected device.

<img width="813" height="842" alt="Screenshot 2025-09-25 112411" src="https://github.com/user-attachments/assets/5e222584-245e-4ddc-b3fb-c82712eaffbf" />

Then I find `antivirus.exe` select the first found, the  scroll through the details and see the destination ip.

<img width="943" height="681" alt="Screenshot 2025-09-25 112458" src="https://github.com/user-attachments/assets/d83576cb-a689-4c85-8f2f-0e2afae9c29e" />

**8. The threat actor logged in via RDP right after the “installer” was downloaded. What is the source IP?**

First I filter for `Event ID 3` then I select find and type in `rdp` then the second found, I see the answer.

<img width="785" height="541" alt="Screenshot 2025-09-25 141430" src="https://github.com/user-attachments/assets/17db37e4-0f63-4b88-ae82-75be08379ae8" />

<img width="641" height="209" alt="Screenshot 2025-09-25 142014" src="https://github.com/user-attachments/assets/c79711ec-b037-43e8-9c28-6c75086a8517" />

<img width="888" height="484" alt="Screenshot 2025-09-25 142110" src="https://github.com/user-attachments/assets/045df1e5-852e-4f7e-bd45-ef1d94ddc7b5" />

**9. This other person downloaded a file and ran it. When was this file run? Timezone UTC (Format YYYY-MM-DD hh:mm:ss)**

I beleive they are talking about that other file in the downloads. `decryptor.exe` I will filter for `Event ID 1` since I am looking for process creation. Then find `decryptor.exe`

<img width="787" height="484" alt="Screenshot 2025-09-25 142553" src="https://github.com/user-attachments/assets/b5497d2f-b25c-4dcc-836f-f4206a464144" />

<img width="578" height="262" alt="Screenshot 2025-09-25 142627" src="https://github.com/user-attachments/assets/8edcba88-cc60-4c18-83bb-d3b041ef79b8" />


The next 7 questions are needing to be ordered from beginning to end.

1. `Sophie downloaded the malware and ran it.`
2. `The downloaded malware encrypted the files on the computer and showed a ransomware note.`
3. `After seeing the ransomware note, Sophie ran out and reached out to you for help.`
4. `While Sophie was away, an intruder logged into Sophie's machine via RDP and started looking around.`
5. `The intruder realized he infected a charity organization. He then downloaded a decryptor and decrypted all the files.`
6. `After all the files are restored, the intruder left the desktop telling Sophie to check her Bitcoin.`
7. `Sophie and I arrive on the scene to investigate. At this point, the intruder was gone.`

<img width="803" height="435" alt="Screenshot 2025-09-25 143153" src="https://github.com/user-attachments/assets/8f530b2a-52ea-400e-878b-5509ccb39ecc" />

