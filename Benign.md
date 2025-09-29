# Benign
Try Hack Me Benign


**1. How many logs are ingested from the month of March, 2022?**

`13959`

I editted the time to only March 2022.

<img width="1897" height="156" alt="Screenshot 2025-09-29 151346" src="https://github.com/user-attachments/assets/fd93caec-4dc0-4b80-8b17-e8d3029fa982" />

**2. Imposter Alert: There seems to be an imposter account observed in the logs, what is the name of that user?**

I used the query `index=win_eventlogs | top limit=11 UserName`

This allowed me to visually see if there are any anomolies. As I can see the account `Amelia` has a second similur account `Amel1a` thats what we are looking for.

<img width="681" height="286" alt="Screenshot 2025-09-29 152113" src="https://github.com/user-attachments/assets/45dc5e46-6ba6-4af6-9729-e68215750f1d" />

**3. Which user from the HR department was observed to be running scheduled tasks?**

To find this I started with a query that narrows down the searches to include a `/create` within the command line. Since this will point to a task creation.

`index=win_eventlogs CommandLine="*/create*"`

<img width="351" height="233" alt="Screenshot 2025-09-29 153002" src="https://github.com/user-attachments/assets/e7f8650f-26e0-49d7-bff6-2a027415491e" />

**4. Which user from the HR department executed a system process (LOLBIN) to download a payload from a file-sharing host.**

This requires you to go to the github and get the binaries, and what to look for. I found that `certutil.exe` is used to download the payload. So I made a query `index=win_eventlogs certutil.exe`

<img width="475" height="264" alt="Screenshot 2025-09-29 153534" src="https://github.com/user-attachments/assets/4e838733-8491-4fed-bdd9-4b73f3300739" />

**5. To bypass the security controls, which system process (lolbin) was used to download a payload from the internet?**

I found this answer in the last question. `certutil.exe`

**6. What was the date that this binary was executed by the infected host? format (YYYY-MM-DD)**

I can get this from the last screenshot.

<img width="896" height="150" alt="Screenshot 2025-09-29 153846" src="https://github.com/user-attachments/assets/3b29f9b3-d6cb-49b9-ad48-8ec48a20e04d" />

**7. Which third-party site was accessed to download the malicious payload?**

In that same entry, the answer is the URL given within the Command Line.

<img width="980" height="43" alt="Screenshot 2025-09-29 154016" src="https://github.com/user-attachments/assets/448fa109-a8a0-43f7-aae2-c1dc9efd40d6" />

**8. What is the name of the file that was saved on the host machine from the C2 server during the post-exploitation phase?**

The answer is given in the last part of the Command Line `benign.exe`

**9. The suspicious file downloaded from the C2 server contained malicious content with the pattern THM{..........}; what is that pattern?**

I copied and pasted the URL within the command line, and found the answer there.

<img width="670" height="831" alt="Screenshot 2025-09-29 154619" src="https://github.com/user-attachments/assets/e94c3442-d9a9-477f-a627-3193f916435a" />

**10. What is the URL that the infected host connected to?**

This is the same URL I just went to for the last question.

`https://controlc.com/e4d11035`

<img width="702" height="427" alt="Screenshot 2025-09-29 154740" src="https://github.com/user-attachments/assets/ce3592fc-3cfc-4ca3-9784-8c671b997449" />











