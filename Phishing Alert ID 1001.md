# Soc-Simulator-Phishing-Unfolded
Soc Simulator Phishing Unfolded from Try Hack Me


# Phishing Alert ID 1001

First looking at the details provided in the ticket.

<img width="1453" height="666" alt="Screenshot 2025-10-08 083855" src="https://github.com/user-attachments/assets/a216a2df-3935-4c21-a475-684f16babc06" />

First thing I will investigate is the recipient, so my first query will be `recipient= michelle.smith@tryhatme.com`

I get 2 entries, first one was the "spam" ticket since it looks very spammy. If someone is offering a free vacation it will be a scam.

There isnt an attachment to inspect.

Next I will query to see if the malicious sender sent anything else with `sender= maximillian@chicmillinerydesigns.de`

I only get the 1 entry confirming the senders address didnt send anything else.

<img width="680" height="286" alt="Screenshot 2025-10-08 093244" src="https://github.com/user-attachments/assets/424e71dd-c7d1-4337-a7db-2c41f8e6fb36" />

Next I just do a quick search to see if the same style of email was sent to anyone with `*| spath subject | search subject="*Your Dream Vacation Awaits*"`

But I only got the 1 entry, I can do my case write up now.

This was a quick one, nothing much to it. It was clearly a spam email, no attachments or links. So just ignore the email and block the sender. Adjust rules for emails asking about free vacations.

<img width="1401" height="836" alt="Screenshot 2025-10-08 093835" src="https://github.com/user-attachments/assets/57442129-c292-4797-bfdb-9b9a58516b75" />



























































