# Soc-Simulator-Phishing-Unfolded

Soc Simulator Phishing Unfolded from Try Hack Me

# Phishing Alert ID 1003

Reading the details of the ticket I can see that an employee responded to a possibly malicious domain.

<img width="1472" height="671" alt="Screenshot 2025-10-10 132855" src="https://github.com/user-attachments/assets/083fdd15-5df3-4f63-9866-75050d96fa5a" />

First I am going to see all emails sent and received by the employee.

`recipient= warner@yahoo.com` I only get the 1 event.

<img width="1903" height="801" alt="Screenshot 2025-10-10 133111" src="https://github.com/user-attachments/assets/44563b62-2c59-4fc7-84a3-f6ae454853fb" />

`sender= warner@yahoo.com` I get nothing

<img width="669" height="236" alt="Screenshot 2025-10-10 133232" src="https://github.com/user-attachments/assets/54880e34-d725-4fa4-9444-58789a3077c5" />

`recipient= support@tryhatme.com` I get 3 events, but nothing related.

<img width="575" height="295" alt="Screenshot 2025-10-10 133333" src="https://github.com/user-attachments/assets/b7af4e92-9286-4dea-884d-bae9a9800e87" />

`direction= outbound warner@yahoo.com` I found the reply I was looking for with this.

Next I see if this same type of email has been sent anywhere else. `Convention Registration Now Open: Hat Trends and Insights`

There is 2 events, I will input this into my SOC tools within the analyst vm.

<img width="1488" height="849" alt="Screenshot 2025-10-10 134336" src="https://github.com/user-attachments/assets/c7804157-826f-4145-b6b5-2a7ffb50fb05" />

All emails came back as clean. `gardner@modishmillinery.com & warner@yahoo.com`

I feel comfortable doing my case write up now, I beilive this is a harmless email they forwarded. Not sure if I have a way with the tools available to see the content of the email. But from what I can see, there is no attachment or links to interact with. So this will be a false positive.

<img width="1374" height="879" alt="Screenshot 2025-10-10 135122" src="https://github.com/user-attachments/assets/08097941-22b6-4555-b5a8-79c062785d0c" />



























