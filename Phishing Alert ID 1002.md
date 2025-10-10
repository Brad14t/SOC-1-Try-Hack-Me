# Soc-Simulator-Phishing-Unfolded

Soc Simulator Phishing Unfolded from Try Hack Me

# Phishing Alert ID 1002

Starting off by getting familiar with the details of the ticket.

<img width="1462" height="705" alt="Screenshot 2025-10-10 104059" src="https://github.com/user-attachments/assets/72b411b5-8e3e-4fa7-a20e-bcfdd7b9616a" />

I will approach this ticket following the NIST guidelines. `Detection and Analysis, Containment, Eradication, Recovery, and Post-Incident Activity.`

**Detection and Analysis**

First inside Splunk I will query for only sysmon events `*| spath datasource | search datasource=sysmon` I get 147 entries 

Next to decrease the number I will include in the search the process.pid in questiuon `* process.pid=3897 | spath datasource | search datasource=sysmon`

I got 2 entries, the first 1 is the issue I am working on. Next I need to confirm if this process and parent process is normal.

After doing some research, the correct working directory is `C:\Windows\system32\` which is good because thats what I have.

Then I found that that child parent relationship is correct, and doesnt show signs of malicous activity.

<img width="949" height="114" alt="Screenshot 2025-10-10 111737" src="https://github.com/user-attachments/assets/d519c63b-8075-4fac-8617-541b6e78bbbe" />

<img width="951" height="100" alt="Screenshot 2025-10-10 111721" src="https://github.com/user-attachments/assets/b9e82877-4baf-489b-9b2e-6d60d527ddd2" />

I feel confident this was a legitimate process. So I will do my case writeup now.

<img width="1373" height="818" alt="Screenshot 2025-10-10 112707" src="https://github.com/user-attachments/assets/90534759-8ba5-40cc-9a45-58894aa28c29" />




































































