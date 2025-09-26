# Introduction-to-SIEM & Investigating with ELK 101 & ItsyBitsy
Try Hack Me Introduction to SIEM process.


**1. What does SIEM stand for?**

`Security Information and Event Management system`

**2. Is Registry-related activity host-centric or network-centric?**

`host-centric` due to regestry logs being created by the local host.

**3. Is VPN related activity host-centric or network-centric?**

`Network-Centric` due to hosts needing to communicate to each for these logs.

**4. In which location within a Linux environment are HTTP logs stored?**

`/var/log/httpd`

**5. Which Event ID is generated when event logs are removed?**

<img width="1035" height="62" alt="Screenshot 2025-09-25 150505" src="https://github.com/user-attachments/assets/abab0d57-6ebc-4fff-b18f-b06f85222824" />

**6. What type of alert may require tuning?**

<img width="1053" height="41" alt="Screenshot 2025-09-25 150616" src="https://github.com/user-attachments/assets/0af71c28-58c3-463c-8540-ffa4b22c9eb0" />

**7. Click on Start Suspicious Activity, which process caused the alert?**

<img width="527" height="158" alt="Screenshot 2025-09-25 150809" src="https://github.com/user-attachments/assets/ee4c8023-6fdf-489e-b1c6-e616bbacac7d" />

`cudominer.exe`

**8. Find the event that caused the alert, which user was responsible for the process execution?**

I click the event to pull up all events, scroll down till I see the process, then I can find the user next to it.

<img width="203" height="271" alt="Screenshot 2025-09-25 150929" src="https://github.com/user-attachments/assets/b24d3fd3-7125-4df7-83db-a2cfc953feb8" />

**9. What is the hostname of the suspect user?**

<img width="632" height="441" alt="Screenshot 2025-09-25 151138" src="https://github.com/user-attachments/assets/5cb4adc3-3594-4638-87dc-08f6991aefce" />

**10. Examine the rule and the suspicious process; which term matched the rule that caused the alert?**

Looking at the rule, I can see it was triggered by having miner in the value.

<img width="478" height="90" alt="Screenshot 2025-09-25 151322" src="https://github.com/user-attachments/assets/d3a941a9-b78f-4060-a911-f23d6e7a8e63" />

**11. What is the best option that represents the event? Choose from the following: - False-Positive - True-Positive**

`True-Positive` due to us knowing this was an actual attack.

**12. Selecting the right ACTION will display the FLAG. What is the FLAG?**

You will get this after answering the last question.

<img width="1079" height="439" alt="Screenshot 2025-09-25 151801" src="https://github.com/user-attachments/assets/8ab0236f-5955-4229-aa52-cde5fbbfd3cb" />


# Investigating with ELK 101

**1. Logstash is used to visualize the data. (yay / nay)**

`nay` because Logstash is for filtering the input.

**2. Elasticstash supports all data formats apart from JSON. (yay / nay)**

`nay` because it can injest JSON.

**3. Select the index vpn_connections and filter from 31st December 2021 to 2nd Feb 2022. How many hits are returned?**

First I select the date range provided.

<img width="719" height="98" alt="Screenshot 2025-09-26 092308" src="https://github.com/user-attachments/assets/caec5bcb-ff67-4d87-94ce-f136bd70a805" />

Then I can see how many entries their are.

<img width="665" height="359" alt="Screenshot 2025-09-26 092348" src="https://github.com/user-attachments/assets/c12f7791-cf50-4599-b7c3-24209f401de8" />

**4. Which IP address has the max number of connections?**

I will filter by `Source_IP` and find the highest percent IP.

<img width="832" height="591" alt="Screenshot 2025-09-26 092519" src="https://github.com/user-attachments/assets/8307ff94-1bc3-4ce7-8e66-011f67aa91eb" />

**5. Which user is responsible for max traffic?**

Filter by `Username` find highest percent

<img width="393" height="541" alt="Screenshot 2025-09-26 092650" src="https://github.com/user-attachments/assets/34272644-1408-477b-a309-1df817540b88" />

**6. Apply Filter on UserName Emanda; which SourceIP has max hits?**

First I filter for `Emanda`

<img width="381" height="250" alt="Screenshot 2025-09-26 092734" src="https://github.com/user-attachments/assets/51ff0318-a6e6-41c0-9054-7b755dcb82ec" />

Then filter by `SourceIP`

<img width="862" height="468" alt="Screenshot 2025-09-26 092749" src="https://github.com/user-attachments/assets/cc6da900-85c4-4ce3-988e-561332bb3bfe" />

**7. On 11th Jan, which IP caused the spike observed in the time chart?**

First I select at the top `Jan 11`

Then filter by `SourceIP`

<img width="1512" height="545" alt="Screenshot 2025-09-26 093021" src="https://github.com/user-attachments/assets/056002e2-2808-48ed-bb09-5875c3fef5d5" />

**8. How many connections were observed from IP 238.163.231.224, excluding the New York state?**

I fikter for the IP given then filter out New York State.

<img width="196" height="148" alt="Screenshot 2025-09-26 093232" src="https://github.com/user-attachments/assets/42144b74-eba1-4db8-b6b9-805778652de2" />

<img width="776" height="153" alt="Screenshot 2025-09-26 093246" src="https://github.com/user-attachments/assets/93fed7bb-4615-41f1-87ad-db0f413127bc" />

**9. Create a search query to filter out the logs from Source_Country as the United States and show logs from User James or Albert. How many records were returned?**

`Source_Country: "United States" AND (UserName: "James" OR "Albert")`

<img width="872" height="354" alt="Screenshot 2025-09-26 093922" src="https://github.com/user-attachments/assets/79e9bea1-4460-43d7-b184-da0e9f5f3327" />

**10. As User Johny Brown was terminated on 1st January 2022, create a search query to determine how many times a VPN connection was observed after his termination.**

First I set the time to the 1st of Jan to now. Then used the filter `UserName: "Johny Brown"`

Only 1 result came back, and thats the answer. But I can confirm by looking into `_index` field. Letting me know the result is a vpn connection

<img width="829" height="656" alt="Screenshot 2025-09-26 094422" src="https://github.com/user-attachments/assets/23b09afc-b14b-4d54-82de-3f2a21bfce19" />

**11. Which user was observed with the greatest number of failed attempts?**

<img width="187" height="205" alt="Screenshot 2025-09-26 095148" src="https://github.com/user-attachments/assets/e3a2dc96-6bd7-4228-beb9-4cd04db4eadc" />

<img width="961" height="265" alt="Screenshot 2025-09-26 095204" src="https://github.com/user-attachments/assets/2c7549d8-42fa-4ec5-8462-5f9198c70983" />

<img width="610" height="253" alt="Screenshot 2025-09-26 095218" src="https://github.com/user-attachments/assets/26b0d098-98b4-4360-b15e-69ff278eeaad" />

<img width="281" height="172" alt="Screenshot 2025-09-26 095232" src="https://github.com/user-attachments/assets/d14fa0eb-d27a-48fb-bb31-ef68f75ea317" />

<img width="598" height="228" alt="Screenshot 2025-09-26 095258" src="https://github.com/user-attachments/assets/8c367690-86e9-470b-855f-5c2b1c6af47a" />

Then add to the Table `UserName` & `action`

<img width="1448" height="611" alt="Screenshot 2025-09-26 095539" src="https://github.com/user-attachments/assets/14c86838-485e-4ad5-9bc3-d18e1b7443cc" />

**12. How many wrong VPN connection attempts were observed in January?**

We can get the answer for this from the last answer.

<img width="1210" height="448" alt="Screenshot 2025-09-26 095737" src="https://github.com/user-attachments/assets/b8ad22e4-4087-4e32-9acb-f6260a0f31a9" />

**13. How many events were returned for the month of March 2022?**

First I filtered by the dates given

<img width="1923" height="484" alt="Screenshot 2025-09-26 102056" src="https://github.com/user-attachments/assets/c07093ef-93f4-4f28-8b6a-bad0dd9adcba" />

# ItsyBitsy

**1. What is the IP associated with the suspected user in the logs?**

First I went to `SourceIP` and tried the onw with the most entries, that was incorrect.

<img width="401" height="273" alt="Screenshot 2025-09-26 103553" src="https://github.com/user-attachments/assets/ece48fea-3dd6-4c19-b793-a5891a80a262" />

Second option is what I am looking for.

**2. The user’s machine used a legit windows binary to download a file from the C2 server. What is the name of the binary?**

I first filter for only the malicous IP.

Then look for `user_agent` value.

<img width="1446" height="473" alt="Screenshot 2025-09-26 103848" src="https://github.com/user-attachments/assets/8c57a13f-a7de-4024-9fc5-ae50d70c0c66" />

**3. The infected machine connected with a famous filesharing site in this period, which also acts as a C2 server used by the malware authors to communicate. What is the name of the filesharing site?**

Looking at the same entry I can find this under the field `host` and the value is the answer.

<img width="1231" height="464" alt="Screenshot 2025-09-26 104015" src="https://github.com/user-attachments/assets/30febef6-7341-4ad1-9235-81fe0ee0221e" />

**4. What is the full URL of the C2 to which the infected host is connected?**

To answer this, we already have the first part, I just add the field `uri`'s value to the end of the `host`

`pastebin.com/yTg0Ah6a`

**5. A file was accessed on the filesharing site. What is the name of the file accessed?**

I enter the url into my search bar and can find the answer there.

**6. The file contains a secret code with the format THM{_____}.**

Scroll down in the website, and find the answer there.

<img width="909" height="416" alt="Screenshot 2025-09-26 104911" src="https://github.com/user-attachments/assets/f3fdf045-ea43-4a38-9555-5f5c9c000d32" />

<img width="758" height="434" alt="Screenshot 2025-09-26 104846" src="https://github.com/user-attachments/assets/aa1b5a0d-31dc-4ad1-aaf9-39115d796483" />








