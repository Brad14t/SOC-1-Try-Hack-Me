# Splunk_THM
This repository will show my progress in furthering my knowledge in Splunk, inside of Try Hack Me's learning and practice.

# Certificates of Completion

![Screenshot 2025-01-22 104153](https://github.com/user-attachments/assets/01385604-6aeb-44eb-a96f-3c1bed7f51f5)


# Splunk Basics

After uploading VPN logs into Splunk on the attack box:

Some answers shown for questions, this will be fixed for the future questions.

I will display my searches (even the incorrect ones, since thats where you learn the most) after the questions.

![Screenshot 2025-01-22 103510](https://github.com/user-attachments/assets/079be11c-79fc-4a1b-9a61-adaeed6fed84)


1. `source="VPN-logs-1663593355154.json" host="VPN_Connections" index="vpn_logs" sourcetype="_json"`

2. `source="VPN-logs-1663593355154.json" host="VPN_Connections" index="vpn_logs" sourcetype="_json" UserName=Maleena`

3. `source="VPN-logs-1663593355154.json" host="VPN_Connections" index="vpn_logs" sourcetype="_json" Source_ip="107.14.182.38"`

4. `source="VPN-logs-1663593355154.json" host="VPN_Connections" index="vpn_logs" sourcetype="_json" Source_Country!=France`

5. `source="VPN-logs-1663593355154.json" host="VPN_Connections" index="vpn_logs" sourcetype="_json" Source_ip="107.3.206.58"`


# Incident Handling in Splunk

Summary of Scenario:

![Screenshot 2025-01-22 110423](https://github.com/user-attachments/assets/85ad51bb-64ab-4377-b0ca-2aea0fa7394c)

**Reconnaissance Phase**

1st search is to narrow search down to any data containing the malicious website: `index=botsv1 imreallynotbatman.com`

Since this is a malicous website we can filter down the results further, looking inside the `sourcetype` I see a `stream:http` which is website logs. 

2nd search to incluse stream:hhtp: `index=botsv1 imreallynotbatman.com sourcetype="stream:http"`

Looking through the side fields, I see `src_ip` and it lists 2 IP's associated with the website logs. 

![Screenshot 2025-01-22 110943](https://github.com/user-attachments/assets/5c8d3986-aa13-42ac-91f5-19e531bd8d29)

Now that the IP address the malicious traffic is coming from is narrowed down. I can move onto the questions.

<img width="914" alt="1" src="https://github.com/user-attachments/assets/6fd5ef02-0892-42a9-aec8-8b314fa7f9fa" />

1. I spent awhile confused on this question but, once you find the `alert.signature` field you can find the field values with the CVE value. 

The search: `index=botsv1 imreallynotbatman.com src_ip="40.80.148.42" sourcetype=suricata`

Inside the field `aler.signature`:

<img width="431" alt="1" src="https://github.com/user-attachments/assets/68690648-6a90-4ba6-926d-d939130c2c34" />

2. To start you need to know CMS stands for content managment system, Im not 100% sure what that means but I think its the source site or app that is hosting the web server.

I am going to start the search with `index=botsv1 imreallynotbatman.com src_ip="40.80.148.42"`

Looking in the fields in the left I notice lots of `http` options, looking through each one till I got to `http.url`

<img width="434" alt="1" src="https://github.com/user-attachments/assets/61ecd7bc-1a02-4438-a2b6-e7e576c9f054" />

In there I notice a lot of `joombla`. Enter into THM and thats the answer.

3. To start to find the webserver used by the attacker, Im not 100% sure whats the best way to start but I know that web scanners send lots of HTTP requests, also look for `404` eventcodes, this is because web scanners look for admin panels, outdated software, or known vulnerabilities.

My 1st search will be: `index=botsv1 imreallynotbatman.com src_ip="40.80.148.42" 404` this narrowed it down to ~4000 results

In the fields I came across the `http_comment` and it proves that there are many http 404 errors. So I will add that to search to narrow it down to ~1200 results.

After that I just selected the very 1st data input, and I got to the src_header after scrolling through and it shows the application used to scan.

<img width="568" alt="1" src="https://github.com/user-attachments/assets/98e1f45d-7e4d-47f9-940b-b17295dcd494" />

4. This one is simple and can be found within the `dest_ip` since that is the website the attacker is accessing.

**Explotation Phase**


















