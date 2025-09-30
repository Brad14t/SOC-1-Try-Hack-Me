# SOC-Alert-8815

I start with reading the writeup/ticket.

<img width="1453" height="835" alt="Screenshot 2025-09-30 130042" src="https://github.com/user-attachments/assets/1d8702fa-243e-47f0-b709-420c0878310c" />

First I will query with the sender, and see if that same user sent anyone else this email. `index=* sender=urgents@amazon.biz`

<img width="957" height="222" alt="Screenshot 2025-09-30 130323" src="https://github.com/user-attachments/assets/45ac6a58-9c04-4e78-aa67-ce7c6e3abfda" />

No other emails from this sender address were detected.

Then I look for any other entries with that url. `index=* bit.ly`

I got 2 responses. And I can see that the email in question, then I can see a firewall block of that URL.

This confirms this is malicous and the network already blocked it. I can confirm by using OSINT tools on the domain, and with internal tools.

<img width="1467" height="752" alt="Screenshot 2025-09-30 130846" src="https://github.com/user-attachments/assets/79eeecae-cffe-43b8-ab80-82491b8a4518" />

I'll finish up with my report.

<img width="1408" height="915" alt="Screenshot 2025-09-30 132000" src="https://github.com/user-attachments/assets/6e999cf3-0959-468d-9e76-54b520690519" />





























