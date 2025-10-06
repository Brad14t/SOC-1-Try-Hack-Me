# Windows Forensics 1 & 2

**1. What is the most used Desktop Operating System right now?**

`Microsoft Windows`

**2. What is the short form for HKEY_LOCAL_MACHINE?**

`HKLM`

<img width="1634" height="101" alt="Screenshot 2025-10-01 114611" src="https://github.com/user-attachments/assets/e39c5a17-c680-4b61-a377-d705a00d46b8" />

**3. What is the path for the five main registry hives, DEFAULT, SAM, SECURITY, SOFTWARE, and SYSTEM?**

`C:\Windows\System32\Config`

<img width="1764" height="369" alt="Screenshot 2025-10-01 115051" src="https://github.com/user-attachments/assets/a49e57f5-2967-4160-8e35-c5231d1cfa0f" />

**4. What is the path for the AmCache hive?**

`C:\Windows\AppCompat\Programs\Amcache.hve`

<img width="1796" height="166" alt="Screenshot 2025-10-01 115140" src="https://github.com/user-attachments/assets/d51c70a2-f963-4f16-9c22-3e3cb066ad2a" />

**5. What is the Current Build Number of the machine whose data is being investigated?**

`19044`

<img width="613" height="202" alt="Screenshot 2025-10-01 131000" src="https://github.com/user-attachments/assets/0388e939-39ec-4e76-bf5a-a375671608fd" />

**6. Which ControlSet contains the last known good configuration?**

`1`

<img width="445" height="174" alt="Screenshot 2025-10-01 131404" src="https://github.com/user-attachments/assets/76f5b20d-8b86-45a8-86f0-47518ed3b4fa" />

**7. What is the Computer Name of the computer?**

`THM-4n6`

<img width="459" height="97" alt="Screenshot 2025-10-01 131746" src="https://github.com/user-attachments/assets/476a4903-c157-4950-b837-d03b34604830" />

**8. What is the value of the TimeZoneKeyName?**

`Pakistan Standard Time`

<img width="798" height="190" alt="Screenshot 2025-10-01 131857" src="https://github.com/user-attachments/assets/712ffb44-a678-491a-add3-76f3294566c3" />

**9. What is the DHCP IP address**

`192.168.100.58`

<img width="613" height="135" alt="Screenshot 2025-10-01 132004" src="https://github.com/user-attachments/assets/62ba392c-8599-4eeb-b701-aaf5b92d3170" />

**10. What is the RID of the Guest User account?**

`501`

<img width="795" height="295" alt="Screenshot 2025-10-01 132256" src="https://github.com/user-attachments/assets/c95065a6-4467-4a52-a79f-872f0f10317f" />

**11. When was EZtools opened?**

`2021-12-01 13:00:34`

<img width="789" height="136" alt="Screenshot 2025-10-01 132556" src="https://github.com/user-attachments/assets/384f2e92-acee-4ff7-9757-68241ba616c1" />

**12. At what time was My Computer last interacted with?**

`2021-12-01 13:06:47`

<img width="792" height="157" alt="Screenshot 2025-10-01 132719" src="https://github.com/user-attachments/assets/9dba6c3d-ac9e-473c-88dd-83140c90fff5" />

**13. What is the Absolute Path of the file opened using notepad.exe?**

`C:\Program Files\Amazon\Ec2ConfigService\Settings`

<img width="798" height="88" alt="Screenshot 2025-10-01 132926" src="https://github.com/user-attachments/assets/b60d8487-8de4-4ce5-b90d-9f0227a26563" />

**14. When was this file opened?**

`2021-11-30 10:56:19`

<img width="795" height="84" alt="Screenshot 2025-10-01 133047" src="https://github.com/user-attachments/assets/26a03a7d-99b1-49a8-865e-e5b99286c18b" />

**15. How many times was the File Explorer launched?**

`26`

<img width="811" height="175" alt="Screenshot 2025-10-01 143612" src="https://github.com/user-attachments/assets/2b8fa594-322f-413a-bf5b-329c636b7792" />

**16. What is another name for ShimCache?**

`AppCompatCache`

<img width="892" height="112" alt="Screenshot 2025-10-01 144115" src="https://github.com/user-attachments/assets/70984ca5-0493-41fe-bcd5-f500765d67fe" />

**17. Which of the artifacts also saves SHA1 hashes of the executed programs?**

`AmCache`

<img width="1824" height="143" alt="Screenshot 2025-10-01 150715" src="https://github.com/user-attachments/assets/a84b3eee-8a89-49d7-9996-d5b52bf46cc5" />

**18. Which of the artifacts saves the full path of the executed programs?**

`BAM/DAM`

<img width="1817" height="271" alt="Screenshot 2025-10-01 151301" src="https://github.com/user-attachments/assets/b7185a19-b9e7-458c-808b-990d55c9ad85" />

**19. What is the serial number of the device from the manufacturer 'Kingston'?**

`1C6F654E59A3B0C179D366AE&0`

<img width="861" height="109" alt="Screenshot 2025-10-01 151423" src="https://github.com/user-attachments/assets/efac705e-d5b4-447d-95cb-86840372d5c4" />

**20. What is the name of this device?**

`Kingston Data Traveler 2.0 USB Device`

<img width="868" height="109" alt="Screenshot 2025-10-01 151610" src="https://github.com/user-attachments/assets/b67f409d-aa3f-4788-a61c-563269d660d4" />

**21. What is the friendly name of the device from the manufacturer 'Kingston'?**

`USB`

<img width="872" height="97" alt="Screenshot 2025-10-01 151741" src="https://github.com/user-attachments/assets/b465b31b-057e-4a4f-80eb-d16c814f9797" />

# Hands on challenge

I start by opening `Registry Explorer` within the given `EZTools` folder.

<img width="499" height="282" alt="Screenshot 2025-10-01 155306" src="https://github.com/user-attachments/assets/10c50cc2-fa63-4bcd-b27d-95adb70b487d" />

Then I want to import a hive, so I select `File > Load Hive > triage > C -> Windows -> System 32 -> config` Then select `DEFAULT`

<img width="925" height="685" alt="Screenshot 2025-10-01 155924" src="https://github.com/user-attachments/assets/7f2b4c27-9b54-4a8e-a7fb-25fd7629620b" />

<img width="481" height="156" alt="Screenshot 2025-10-01 155937" src="https://github.com/user-attachments/assets/46099ac9-49d1-4b94-85b4-8d1b4504cd8b" />

<img width="919" height="699" alt="Screenshot 2025-10-01 155955" src="https://github.com/user-attachments/assets/413fadd6-e1e8-4d62-a6de-cbc573b58863" />

<img width="384" height="155" alt="Screenshot 2025-10-01 160021" src="https://github.com/user-attachments/assets/174072db-93c9-450d-a5c6-042eea348983" />

Now I have loaded my first hive.

<img width="833" height="426" alt="Screenshot 2025-10-01 160033" src="https://github.com/user-attachments/assets/7d4a291a-3f43-41f1-b592-717ec7cd6e98" />

Next I will load the SAM hive to get user information.

<img width="904" height="350" alt="Screenshot 2025-10-03 112056" src="https://github.com/user-attachments/assets/583c47ad-59d5-495a-a86c-14f2c5f7b75f" />

Then I go to the location of user info, I can see the general account and groups, but below I can see the user created accounts.

<img width="792" height="334" alt="Screenshot 2025-10-03 112440" src="https://github.com/user-attachments/assets/98ffa735-d6b9-49b7-a56b-abdd427eed12" />

**22. How many user created accounts are present on the system? **

`3` I can see this from my last screenshot.

**23. What is the username of the account that has never been logged in?**

In that same page, I will remove all the colomns other than the user, logon times, and last login.

I can see that `thm-user2` hasnt logged in.

<img width="928" height="299" alt="Screenshot 2025-10-03 114545" src="https://github.com/user-attachments/assets/f4477bd5-16f5-4156-b25f-fd609063fe50" />

**24. What's the password hint for the user THM-4n6?**

In the same menu, I focus on the password hin column.

`count`

<img width="346" height="323" alt="Screenshot 2025-10-03 120108" src="https://github.com/user-attachments/assets/6dc84e15-c3ad-4197-bce3-c9c91c6b51f0" />

**25. When was the file 'Changelog.txt' accessed?**

First I read up on Task 8 that covered user info.

First I went to `File Explorer` and showed hidden items.

Then I open File Explorer as admin.

Then back in the Registry Explorer tool and open the `NTUSER.DAT` from `C:/users/THM-4n6`

<img width="906" height="706" alt="Screenshot 2025-10-03 130813" src="https://github.com/user-attachments/assets/f9345d56-3c69-4372-b20c-b7c9da303f79" />

Then the path I took is `ROOT > SOFTWARE > Microsoft > Windows > CurrentVersion > Explore > .txt`

<img width="958" height="276" alt="Screenshot 2025-10-03 132522" src="https://github.com/user-attachments/assets/db3dbd2a-f967-4944-9af0-e6966a8ed81f" />

**26. What is the complete path from where the python 3.8.2 installer was run?**

First after reading up on some documentation, I tried using `Userassist, ShimCache, and AMCache` all went no where. I then found someone saying to try `RecentApps`

And that brought me to the right place.

<img width="1279" height="569" alt="Screenshot 2025-10-03 133742" src="https://github.com/user-attachments/assets/89149644-6189-4040-b85f-ebd3ddbbd876" />

**27. When was the USB device with the friendly name 'USB' last connected?**

To find this I didnt come at it in a special way. I just searched `usb` and was able to find the answer there.

<img width="959" height="350" alt="Screenshot 2025-10-03 134403" src="https://github.com/user-attachments/assets/5f204ac9-fc95-462d-8424-007e9e28b12c" />

# Windows Forensics 2

**1. How many addressable bits are there in the FAT32 file system?**

`28 bits`

<img width="1791" height="214" alt="Screenshot 2025-10-06 110753" src="https://github.com/user-attachments/assets/d945189a-0b2d-4025-9604-233b49bdb901" />


**2. What is the maximum file size supported by the FAT32 file system? (In GB)**

`4`

<img width="1829" height="88" alt="Screenshot 2025-10-06 111036" src="https://github.com/user-attachments/assets/6e4c4eee-d324-43e4-abbd-3f6d8764b7b5" />

**3. Which file system is used by digital cameras and SD cards?**

`EXFat`

<img width="1803" height="155" alt="Screenshot 2025-10-06 111118" src="https://github.com/user-attachments/assets/91ea95a9-ca3b-4793-b8f1-99729c947c8a" />


**4. Parse the $MFT file placed in C:\users\THM-4n6\Desktop\triage\C\ and analyze it. What is the Size of the file located at .\Windows\Security\logs\SceSetupLog.etl**

First I opened a admin CMD and starting with

I navigate to `C:\Users\THM-4n6\Desktop\Eztools` then run `MFTECmd.exe`

Once running I will run the following command to analyze the `$MFT` file `MFTECmd.exe -f C:\Users\THM-4n6\Desktop\triage\C\$MFT --csv C:\Users\THM-4n6\Desktop`

Then I opened the new csv file in `EZViewer` and searched the files name, found the answer there.

<img width="571" height="41" alt="Screenshot 2025-10-06 120116" src="https://github.com/user-attachments/assets/556faf9d-a674-4fda-b262-6ded9a1b3a99" />

**5. What is the size of the cluster for the volume from which this triage was taken?**

After some digging in the CSV file, I realized the answer wont be there. I found I need to analyze the `$BOOT` file. I used the command `MFTECmd.exe -f C:\Users\THM-4n6\Desktop\triage\C\$BOOT` and I was able to find the cluster size in the output.

<img width="916" height="625" alt="Screenshot 2025-10-06 120826" src="https://github.com/user-attachments/assets/664c6232-65eb-479e-8712-c1be2289822b" />

**6. There is another xlsx file that was deleted. What is the full name of that file?**

First I go through the steps of setting up `AutoSpy`

<img width="1278" height="810" alt="Screenshot 2025-10-06 130810" src="https://github.com/user-attachments/assets/7994482d-c766-404a-b247-39abb1effe92" />

<img width="1263" height="804" alt="Screenshot 2025-10-06 130823" src="https://github.com/user-attachments/assets/6696b16c-94cc-4af6-bff9-21035ac19db3" />

<img width="1271" height="819" alt="Screenshot 2025-10-06 131119" src="https://github.com/user-attachments/assets/1f8813a0-dcb0-4c47-bc3f-24702446c72b" />

<img width="1269" height="801" alt="Screenshot 2025-10-06 131200" src="https://github.com/user-attachments/assets/3cc90ba2-1e2c-4539-a8c2-929d1f3fe20e" />

<img width="1254" height="566" alt="Screenshot 2025-10-06 131557" src="https://github.com/user-attachments/assets/4d21bf3a-6a1d-4a05-90b4-8502603b3220" />

I then select the usb I uploaded, scrolled down and saw the files with the red X, this signifies that the file was deleted.

<img width="406" height="282" alt="Screenshot 2025-10-06 131939" src="https://github.com/user-attachments/assets/cd54a881-f47b-41ff-9277-d1384e10add3" />

**7. What is the name of the TXT file that was deleted from the disk?**

I can find the answer right below the last answer.

<img width="444" height="292" alt="Screenshot 2025-10-06 132044" src="https://github.com/user-attachments/assets/4071d498-e915-45e3-8582-2dc07f3da575" />

**8. Recover the TXT file from Question #2. What was written in this txt file?**

I first right click the file, then `extract` then read the file.

<img width="347" height="125" alt="Screenshot 2025-10-06 132143" src="https://github.com/user-attachments/assets/941dedae-9cf5-4395-b6b9-2bcbcd49e8d2" />

**9. How many times was gkape.exe executed?**

You dont have to save it to a file, I just did it for easy access.

`PECmd.exe -f C:\Users\THM-4n6\Desktop\triage\C\Windows\prefetch\GKAPE.EXE-E935EF56.pf --csv C:\Users\THM-4n6\Desktop`

Then I open the csv file and see how many times that file was executed.

<img width="1182" height="311" alt="Screenshot 2025-10-06 140656" src="https://github.com/user-attachments/assets/ddad0ab9-7a41-43de-997a-d5705388eba2" />

**10. What is the last execution time of gkape.exe**

I can see the answer from the last screenshot.

`12/01/2021 13:04`

**11. When Notepad.exe was opened on 11/30/2021 at 10:56, how long did it remain in focus?**

First command I used was

`WxTCmd.exe -f C:\Users\THM-4n6\Desktop\triage\C\Users\THM-4n6\AppData\Local\ConnectedDevicesPlatform\L.THM-4n6\ActivitiesCache.db — csv C:\Users\THM-4n6\Desktop`

Then I opened the outputted csv into `EZViewer` There I can find the answer.

`00:00:41`

<img width="1648" height="776" alt="Screenshot 2025-10-06 142545" src="https://github.com/user-attachments/assets/04398134-9a88-4d74-b8c1-496930d2c795" />

**12. What program was used to open C:\Users\THM-4n6\Desktop\KAPE\KAPE\ChangeLog.txt?**

For this one I will use the jumplist option. In the cmd I ran

`JLECmd.exe -d C:\Users\THM-4n6\Desktop\triage\C\Users\THM-4n6\AppData\Roaming\Microsoft\Windows\Recent\AutomaticDestinations -- csv C:\Users\THM-4n6\Desktop`

Then opening the outputted file I can see the answer provided. `12/1/2021 13:01`

![1_lqyxUoXRtr7-BBETtqrALw](https://github.com/user-attachments/assets/f00a1ed3-707c-4939-9808-51e5346d1e15)

**13. When was the above-mentioned folder first opened?**

Looking at the creation date from last screenshot I can find this answer.

`12/1/2021 12:31`

**14. Which artifact will tell us the first and last connection times of a removable drive?**

`Setupapi.dev.log`

<img width="876" height="85" alt="Screenshot 2025-10-06 151400" src="https://github.com/user-attachments/assets/8dcbb3b1-d9f9-4fa5-97a9-38e9b3e786f1" />

<img width="1039" height="447" alt="Screenshot 2025-10-06 151437" src="https://github.com/user-attachments/assets/dbcbf2d7-2b60-49fc-bbd6-715b75c33b77" />


















