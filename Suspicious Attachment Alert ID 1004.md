# Soc-Simulator-Phishing-Unfolded

Soc Simulator Phishing Unfolded from Try Hack Me

# Suspicious Attachment Alert ID 1004

First thing I notice looking at the details of this ticket is the suspicious attachment. 

<img width="1469" height="646" alt="Screenshot 2025-10-10 140009" src="https://github.com/user-attachments/assets/79d3c4b1-8ad7-489c-adad-29846d9571bc" />

First thing I will do is search for anything with `forceupdate.ps1`

I got 4 events. The 1st one is the original suspicious email. 2nd was the employee replying. 3rd is the user downloading the attachent. 4th is duplicate of the 1st one.

<img width="1466" height="761" alt="Screenshot 2025-10-10 140437" src="https://github.com/user-attachments/assets/9d618a8f-66e6-4ba9-b7de-ab15f816b20e" />

Since I can see they downloaded the file, I will immediatly check if the file is safe with the tools provided within thr analyst vm.

It came back clean for `TrDetectThis` just to dowble check I will run the hash through `VirusTotals`

<img width="1021" height="657" alt="Screenshot 2025-10-10 141003" src="https://github.com/user-attachments/assets/c196b769-1310-4099-949a-0d4af7393942" />

Nothing came back from VirusTotal.

I also ran the senders email through to check if anyone has found it malicous, and they came back as clean also.

I will continue with my case report, as this was a false positive. Another thing to note is both emails are on the compony employee list.

<img width="1374" height="866" alt="Screenshot 2025-10-10 141508" src="https://github.com/user-attachments/assets/3c0102fc-2f41-424c-ae3c-f2b1bcac4f17" />






































