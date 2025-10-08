# Soc-Simulator-Phishing-Unfolded
Soc Simulator Phishing Unfolded from Try Hack Me


# Phishing Alert ID 1000

First I start by reading the details to the phishing alert.

<img width="1452" height="628" alt="Screenshot 2025-10-07 092104" src="https://github.com/user-attachments/assets/f9b0d24b-0b95-4351-88be-815e09091b5e" />

First details I can gather:

From SOC lead informing us that the detection rule still needs fine tuning, so I just need to make sure to check to make sure its a true positive.

Time of alert: 10/07/2025 17:14:52.195

Suspicious looking subject line: You've Won a Free Trip to Hat Wonderland - Click Here to Claim

Sender: boone@hatventuresworldwide.online

Recipient: miguel.odonnell@tryhatme.com

Then I clicked the playbook link, this helps in gathering artifacts.

Step 1 is to assign the ticket, which I did. 

Step 2 is just gather general knowledge on what I have so far. Which I did, Ill move to Step 3 which is to analyze the email further.

First I will open Splunk, first query I used was `recipient = miguel.odonnell@tryhatme.com` to see all emails sent to this user. I get 6 events.

From the below events I can see this user gets lots of SPAM emails from random addresses. 

<img width="1477" height="782" alt="Screenshot 2025-10-07 094451" src="https://github.com/user-attachments/assets/d51f1c6d-6542-46ce-b6c4-31368302027e" />

<img width="1500" height="800" alt="Screenshot 2025-10-07 094521" src="https://github.com/user-attachments/assets/233861e5-f209-4dac-a098-d7418e0a292c" />

<img width="1485" height="786" alt="Screenshot 2025-10-07 094532" src="https://github.com/user-attachments/assets/de470883-5f1d-4d1c-b45e-547a7baf45f3" />

I will gather the emails that spent spam, to block in the future.

boone@hatventuresworldwide.online
connolly@customcrownhats.org
elle@gmail.com	
gamble@fashionindustrytrends.xyz
laiba@headwearconventionworld.net
sharp@hatsontherise.online

Next I will see if the sender email address sent any more spam emails out. `sender= boone@hatventuresworldwide.online`

I only got the 1 email, which is the one Im are investigating.

Next I will query each email in the list above to see if they sent anything else.

`sender= connolly@customcrownhats.org`
`sender= elle@gmail.com`
`sender= gamble@fashionindustrytrends.xyz`
`sender= laiba@headwearconventionworld.net`
`sender= sharp@hatsontherise.online`

Only the 1 event for each.

Ive gathered enough information to say this was a malicous email, it is spam. No links to click on or attachments so nothing to worry about there. I will write my case report now.

`Time of activity: 10/07/2025 17:14:52.195`

`List of Affected Entities: miguel.odonnell@tryhatme.com`

`Reason for Classifying as True Positive: User had multiple spam emails. All saying fake information. I would not escalate the issue, unless it would be to continue fine tuning rule for spam email blocking.`

`Reason for Escalation:  I would not escalate the issue, unless it would be to continue fine tuning rule for spam email blocking.`

`Recommended Remediation Actions: Continue fine tuning rule for spam email blocking.`

`List of Attack Indicators:`
boone@hatventuresworldwide.online
connolly@customcrownhats.org
elle@gmail.com	
gamble@fashionindustrytrends.xyz
laiba@headwearconventionworld.net
sharp@hatsontherise.online`













































