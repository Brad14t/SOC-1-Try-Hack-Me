# SOC-Alert-8817

Starting off with looking over the provided details.

`Ticket: Inbound Email Containing Suspicous External Link`

<img width="1461" height="799" alt="Screenshot 2025-09-30 134501" src="https://github.com/user-attachments/assets/fd841ec9-1fc7-4f01-b768-439897905204" />

Starting off I can almost say this email is not real, and it is malicous. Sender IP `no-reply@m1crosoftsupport.co`

My first query will to see if this sender address sent anything else. `index=* sender=no-reply@m1crosoftsupport.co`

I only see the email in question, nothing new.

<img width="1906" height="934" alt="Screenshot 2025-09-30 135222" src="https://github.com/user-attachments/assets/d6a958dd-1194-4a22-9bbc-55b31d9a9e2e" />

Then I query the URL given within the email `index=* https://m1crosoftsupport.co/login`

I get 2 events, and 1 is a firewall allowing the web traffic. Which to me as of now is not a good look. In a real world example I would escalte from here. But I still have to confirm if the URL is malicous.

<img width="1468" height="851" alt="Screenshot 2025-09-30 135539" src="https://github.com/user-attachments/assets/5d76c5aa-e803-42f6-a8fe-b0107eebde70" />

Ill collect some artifacts now:

Malicous destination IP: `45.148.10.131`
Malicous Email: `no-reply@m1crosoftsupport.co`
User affected: `c.allen@thetrydaily.thm` `10.20.2.25`
URL: `https://m1crosoftsupport.co/login`

Next I query the bad IP address to see if it was found anywhere else. `index=* 45.148.10.131` 

Nothing new came up. I will start my case write up now

I will run my artifacts to confirm them as malicous.

<img width="1218" height="520" alt="Screenshot 2025-09-30 141046" src="https://github.com/user-attachments/assets/0a6961bc-4e95-490b-bf20-7c93ca2667df" />

<img width="1256" height="549" alt="Screenshot 2025-09-30 141228" src="https://github.com/user-attachments/assets/df95d17e-0bd5-462c-b315-7b3ccbeb1fc3" />

<img width="1460" height="931" alt="Screenshot 2025-09-30 141614" src="https://github.com/user-attachments/assets/8e30494a-1f28-4490-9283-9bbf68c21f15" />




































