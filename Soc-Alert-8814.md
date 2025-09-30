# Soc-Alert-Malicous-Email-1
Try Hack Me Soc Simulator

First alert that came through was an `Inbound Email Conataining Suspicious Link`

<img width="1464" height="779" alt="Screenshot 2025-09-30 085628" src="https://github.com/user-attachments/assets/e46ed4d3-1b35-4d4b-9eb4-88d9f69ae93b" />

First just to understand how this "company" handles alerts, I will select the playbook link.

Step 1 is to assign the ticket to myself. Which is done.

<img width="343" height="111" alt="Screenshot 2025-09-30 085747" src="https://github.com/user-attachments/assets/d237ba94-fb62-436a-af24-adaad60ad965" />

Step 2 is Alert Triaging or just gathering all the information regarding this issue.

<img width="981" height="860" alt="Screenshot 2025-09-30 085834" src="https://github.com/user-attachments/assets/6fdf368a-4bb7-4931-b835-65a0de55b189" />

I will adjust the time to when the email came in.

<img width="969" height="231" alt="Screenshot 2025-09-30 090120" src="https://github.com/user-attachments/assets/8398fb1d-1930-4322-8ded-139669270ea1" />

Then I will query with all indexes, and the provided sender and receiver.

`index=* recipient=j.garcia@thetrydaily.thm sender=onboarding@hrconnex.thm`

This gives me 2 results.

I notice the url given, and made a new query to seer if this email was sent to anyone else.

`index=* hrconnex` provided 3 results, 1 from earlier was another user asking the IT team to check if user has received the email in this issue.

Ill start writing things down for the playbook:

`Sender: onboarding@hrconnex.thm`
`Subject: Inbound Email Conataining Suspicious Link`
`Recipient: j.garcia@thetrydaily.thm
`Delivery time: 09/30/2025 16:52:34.439`

Step 3 of the playbook is to analyze email artifacts. 

Check reputation of sender, I checked Virus Total, WhoIS, AlienVault, and I didnt find anything suspicious about the domain and URL provided.

Review attachments, no attachments to review.

Step 4 is to investigate related reports. I will start by seeing if this sender sent anything else `index=* sender=onboarding@hrconnex.thm`

The same 2 results came up, proving this didnt go anywhere else. SO far everything points to a false positive.

Now I'll start to fill out case report.

<img width="788" height="384" alt="Screenshot 2025-09-30 092354" src="https://github.com/user-attachments/assets/3e29dfef-7695-49fa-b4b1-0964afe1d869" />

<img width="1402" height="860" alt="Screenshot 2025-09-30 092616" src="https://github.com/user-attachments/assets/279c698f-6856-447b-8ad4-98f96ce32f7b" />









































































