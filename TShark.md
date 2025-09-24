# THM-TShark
This will be my process through the Try Hack Me sections TShark: The Basics, TShark: CLI Wireshark, TShark Challenge 1, and TShark Challenge 2.

`49 Total Questions`

**1. View the details of the demo.pcapng file with "capinfos". What is the "RIPEMD160" value?**

`capinfos demo.pcapng`

<img width="854" height="200" alt="Screenshot 2025-09-04 123150" src="https://github.com/user-attachments/assets/fab11656-78f0-465a-b59b-45356d4d3e04" />

**2. What is the installed TShark version in the given VM?**

`tshark -v`

<img width="788" height="92" alt="Screenshot 2025-09-04 123423" src="https://github.com/user-attachments/assets/6aa1a9b8-f876-4d10-9d7b-b1f4fad50076" />

**3. List the available interfaces with TShark. What is the number of available interfaces in the given VM?**

`tshark -D`

<img width="742" height="373" alt="Screenshot 2025-09-04 123655" src="https://github.com/user-attachments/assets/15207323-53b1-4965-ae0e-36139e31318f" />

**4. Read the "demo.pcapng" file with TShark. What are the assigned TCP flags in the 29th packet?**

`tshark -r demo.pcapng -c 29` this command reads the pcap, then stops counting after the 29th packet. I can see the flags after command.

<img width="1055" height="73" alt="Screenshot 2025-09-04 124211" src="https://github.com/user-attachments/assets/970b83e1-5a78-4dbb-94d9-c36eafb2d62d" />

**5. What is the "Ack" value of the 25th packet?**

`tshark -r demo.pcapng -c 25 -V` This reads till the 25th packet and in verbose mode, then I can see the value there.

<img width="1083" height="88" alt="Screenshot 2025-09-04 124645" src="https://github.com/user-attachments/assets/df99ec89-182b-40c1-a8b0-506f42f946b1" />

**6. What is the "Window size value" of the 9th packet?**

`tshark -r demo.pcapng -c 9 -V`

<img width="446" height="130" alt="Screenshot 2025-09-04 124751" src="https://github.com/user-attachments/assets/63784b89-a1d8-436a-ad24-9a103e6249b9" />

**7. Which parameter can help analysts to create a continuous capture dump?**

<img width="691" height="714" alt="Screenshot 2025-09-04 125849" src="https://github.com/user-attachments/assets/12e54725-6ca4-4bfd-8698-acb3a0bfe123" />

**8. Can we combine autostop and ring buffer parameters with TShark? y/n**

<img width="712" height="214" alt="Screenshot 2025-09-04 125921" src="https://github.com/user-attachments/assets/39642e40-d3c4-432f-b267-2fb65a4e1398" />

**9. Which parameter is used to set "Capture Filters"?**

<img width="679" height="128" alt="Screenshot 2025-09-04 130029" src="https://github.com/user-attachments/assets/0c8b9d86-d5d2-4857-8e34-671888405996" />

**10. Which parameter is used to set "Display Filters"?**

<img width="907" height="104" alt="Screenshot 2025-09-04 130107" src="https://github.com/user-attachments/assets/46da45ba-2da0-49e0-b313-0f4868f80129" />

**11. What is the number of packets with SYN bytes?**

First open a terminal and I ran `tshark -f "host 10.10.10.10"

Then open another terminal and I ran `curl -v 10.10.10.10` to send some http data to generate data for the 1st terminal.

After I ran the second command, returning to the 1st terminal, I can now see the packets and I can also see which ones are SYN packets.

<img width="1072" height="645" alt="Screenshot 2025-09-04 135526" src="https://github.com/user-attachments/assets/c2fbf6a7-07e3-489f-8c57-d910689412cf" />

**12. What is the number of packets sent to the IP address "10.10.10.10"?**

On the terminal 1 I run `tshark -Y "ip.dst == 10.10.10.10"`

Then on the second terminal I ran `curl -v 10.10.10.10` and I can count that their is 7 packets sent to that IP.

<img width="1074" height="466" alt="Screenshot 2025-09-04 142831" src="https://github.com/user-attachments/assets/fbbb8aa9-8958-435f-89e6-bb5b5235addd" />

**13. What is the number of packets with ACK bytes?**

I ran on the first terminal `tshark -f "host 10.10.10.10"` then on the second terminal `curl -v 10.10.10.10`

Then I can visably see the 8 ACK packets.

<img width="1060" height="673" alt="Screenshot 2025-09-04 143613" src="https://github.com/user-attachments/assets/1597f260-bc2f-4dcc-9c2f-f90d46b8b6a7" />

**14. What is the number of packets with a "65.208.228.223" IP address?**

`tshark -r demo.pcapng -Y 'ip.addr == 65.208.228.223' | nl`

<img width="1080" height="699" alt="Screenshot 2025-09-04 144436" src="https://github.com/user-attachments/assets/da30b50d-e4fb-45e6-b89d-652cf7d0890d" />

**15. What is the number of packets with a "TCP port 3371"?**

`tshark -r demo.pcapng -Y 'tcp.port == 3371` | nl`

<img width="1085" height="544" alt="Screenshot 2025-09-04 144712" src="https://github.com/user-attachments/assets/c0f10a85-3e74-4882-9e5d-2e383ee36524" />

**16. What is the number of packets with a "145.254.160.237" IP address as a source address?**

`tshark -r demo.pcapng -Y 'ip.src.addr == 145.254.160.237' | nl`

<img width="1057" height="695" alt="Screenshot 2025-09-04 145113" src="https://github.com/user-attachments/assets/cbcfe6e9-c9d0-4b68-960d-d5aaa325a59e" />

<img width="973" height="437" alt="Screenshot 2025-09-04 145308" src="https://github.com/user-attachments/assets/2c3aefb9-62f9-466e-a180-0dc5311feb64" />

**17. Use the "write-demo.pcap" to answer the questions. What is the byte value of the TCP protocol?**

`tshark -r write-demo.pcap -z io,phs -q` to show protocals

<img width="1062" height="342" alt="Screenshot 2025-09-05 101619" src="https://github.com/user-attachments/assets/edfeba28-d806-4b1d-ba5d-bc57e8f41ad1" />

**18. In which packet lengths row is our packet listed?**

`tshark -r write-demo.pcap -z plen,tree -q`

<img width="1087" height="565" alt="Screenshot 2025-09-05 101939" src="https://github.com/user-attachments/assets/ae4e87ad-0859-4d2c-ab2b-d96dc0c178e6" />

**19. What is the summary of the expert info?**

`tshark -r write-demo.pcap -z expert -q`

<img width="1094" height="288" alt="Screenshot 2025-09-05 102103" src="https://github.com/user-attachments/assets/292bde1d-4f33-48f4-a63b-32ef2e92fd54" />

**20. Use the "demo.pcapng" to answer the question. List the communications. What is the IP address that exists in all IPv4 conversations? Enter your answer in defanged format.**

`tshark -r demo.pcapng -z con, ip -q`

<img width="1094" height="506" alt="Screenshot 2025-09-05 103337" src="https://github.com/user-attachments/assets/bcd709e2-2d5d-40c1-a916-a2366ef71f80" />

**21. Use the "demo.pcapng" to answer the questions. Which IP address has 7 appearances? Enter your answer in defanged format.**

`tshark -r demo.pcapng -z ip_hosts,tree -q`

<img width="1069" height="638" alt="Screenshot 2025-09-05 103717" src="https://github.com/user-attachments/assets/6110e25c-e7d2-49cf-96ce-a42f023e175e" />

**22. What is the "destination address percentage" of the previous IP address?**

`tshark -r demo.pcapng -z dests,tree -q`

<img width="360" height="120" alt="Screenshot 2025-09-05 104016" src="https://github.com/user-attachments/assets/8541acf4-6f51-418d-b157-90a85ed3b7d7" />

**23. Which IP address constitutes "2.33% of the destination addresses"? Enter your answer in defanged format.**

I can find this answer in the same page as the last question.

<img width="354" height="91" alt="Screenshot 2025-09-05 104142" src="https://github.com/user-attachments/assets/f3b695c4-ef2c-433a-9c65-38dc9b0aa477" />

**24. What is the average "Qname Len" value?**

`tshark -r demo.pcapng -z dns,tree -q`

<img width="710" height="75" alt="Screenshot 2025-09-05 104434" src="https://github.com/user-attachments/assets/1e27ca4e-bd31-48be-9802-8e2a06d234ef" />

**25. Follow the "UDP stream 0". What is the "Node 0" value? Enter your answer in defanged format.**

`tshark -r demo.pcapng -z follow,udp,ascii,0 -q`

<img width="1074" height="191" alt="Screenshot 2025-09-05 110316" src="https://github.com/user-attachments/assets/68b1e470-ca9f-4884-976b-74ab45ebc2af" />

**26. Follow the "HTTP stream 1". What is the "Referer" value? Enter your answer in defanged format.**

`tshark -r demo.pcapng -z follow,http,ascii,1 -q`

<img width="647" height="41" alt="Screenshot 2025-09-05 111446" src="https://github.com/user-attachments/assets/2fee9a76-181d-4600-9bc1-cf0ca145b833" />

<img width="1231" height="668" alt="Screenshot 2025-09-05 111453" src="https://github.com/user-attachments/assets/0a5ccaf3-83cd-4187-abaf-151c7ef168d4" />

**27. Use the "credentials.pcap" to answer the question. What is the total number of detected credentials?**

`tshark -r credentials.pcap -z credentials -q | nl` and count the lines with Credential values.

<img width="1060" height="725" alt="Screenshot 2025-09-05 111731" src="https://github.com/user-attachments/assets/03dc3149-e965-4a08-8f3f-e8d7ec71ebd4" />

**28. What is the HTTP packet number that contains the keyword "CAFE"?**

`tshark -r demo.pcapng -Y 'http contains "CAFE"'

<img width="1073" height="137" alt="Screenshot 2025-09-05 123555" src="https://github.com/user-attachments/assets/0a5ad315-887a-42bb-9181-19a0d7c0c349" />

**29. Filter the packets with "GET" and "POST" requests and extract the packet frame time. What is the first time value found?**

`tshark -r demo.pcapng -Y 'http.request.method == GET || http.request.method == POST' -T fields -e frame.time`

**30. What is the total number of unique hostnames?**

`tshark -r hostnames.pcapng -T fields -e dhcp.option.hostname | sort -r | uniq -c | awk NF | sort -r | nl`

Count the lines and minus the 1st entry because it doent have a value.

<img width="1095" height="365" alt="Screenshot 2025-09-05 130012" src="https://github.com/user-attachments/assets/ab1e24e7-bbba-4b7e-b2c2-f440595ddc0e" />

**31. What is the total appearance count of the "prus-pc" hostname?**

`tshark -r hostnames.pcapng -T fields -e dhcp.option.hostname | awk NF | sort -r | uniq -c | sort -r`

The main search is looking for hostnames, then I remove empty lines, sort recursivly, only receive uniq values, then sorting again.

<img width="1083" height="195" alt="Screenshot 2025-09-05 131714" src="https://github.com/user-attachments/assets/56abddf4-befd-46d6-8d65-fddbf35314d1" />

**32. What is the total number of queries of the most common DNS query?**

`tshark -r dns-queries.pcap -T fields -e dns.qry.name | awk NF | sort -r | uniq -c | sort -r`

Same as before but looking for DNS queries.

<img width="1079" height="214" alt="Screenshot 2025-09-05 131851" src="https://github.com/user-attachments/assets/ea402b78-1fcc-4e51-9bbe-848e5b483405" />

**33. What is the total number of the detected "Wfuzz user agents"?**

`tshark -r user-agents.pcap -Y 'http.user_agent contains "Wfuzz"' | nl` or `tshark -r user-agents.pcap -Y 'http.user_agent contains "Wfuzz"' | wc -l`

<img width="1077" height="109" alt="Screenshot 2025-09-05 132615" src="https://github.com/user-attachments/assets/de5d5b1a-c85a-4ecf-962d-d03a1dda5c41" />

**34. What is the "HTTP hostname" of the nmap scans? Enter your answer in defanged format.**

`tshark -r user-agents.pcap -T fields -e http.host | sort -r | uniq -c | sort -r`

Then I saw the most used IP, and defanged it.

<img width="1089" height="352" alt="Screenshot 2025-09-05 132820" src="https://github.com/user-attachments/assets/01fc663a-d482-479d-9e9f-6cc04877f472" />

<img width="1285" height="443" alt="Screenshot 2025-09-05 132937" src="https://github.com/user-attachments/assets/a67a7e0a-604d-455d-b276-b83ab9c30cc6" />


**35. Investigate the contacted domains. Investigate the domains by using VirusTotal. According to VirusTotal, there is a domain marked as malicious/suspicious. What is the full URL of the malicious/suspicious domain address? Enter your answer in defanged format.**

First I want to run a command to extract DNS queries.

`tshark -r teamwork.pcap -Y "dns.flags.response eq 0" -T fields -e dns.qry.name | sort | uniq`

This reads the pcap, using -Y for display filters, then I use the dns response flag as the filter and I use eq 0 for only queires not responses. Then I am using -e to output that field, then I sort and only want thw unique entries. And there I can find the answer. I confirm this is the most used malicous query domain by taking the `uniq` off and seeing who has the most entries.

<img width="1092" height="706" alt="Screenshot 2025-09-08 095941" src="https://github.com/user-attachments/assets/4f64c277-6146-4f9d-8765-89701eb406da" />

And I can confirm its a malicous domain by checking in Virus Total.

**36. When was the URL of the malicious/suspicious domain address first submitted to VirusTotal?**

Pasting the URL into Virus total under history I can see the date its been fist submitted.

![URL-first-submitted-on-VirusTotal-1300x680 png](https://github.com/user-attachments/assets/05edf578-9253-43b4-8390-2e981617cea5)

**37. Which known service was the domain trying to impersonate?**

I can see this in the malicous URL, it is paypal.

**38. What is the IP address of the malicious domain? Enter your answer in defanged format.**

I can find this in Virus Total in the relations tab.

<img width="969" height="362" alt="Screenshot 2025-09-08 102043" src="https://github.com/user-attachments/assets/362664aa-5c2a-4086-8538-fe9b25af7c59" />

<img width="1125" height="636" alt="Screenshot 2025-09-08 102054" src="https://github.com/user-attachments/assets/fffc6687-f12e-4ddf-b152-1e6f10b2b3cc" />

**39. What is the email address that was used? Enter your answer in defanged format. (format: aaa[at]bbb[.]ccc)**

First thing I need to do is find all the http packets with .com so I can filter for logins.

Command used `tshark -r teamwork.pcap -Y "http contains .com"` And I see a packet with a `.Login` 

<img width="1072" height="297" alt="Screenshot 2025-09-08 102653" src="https://github.com/user-attachments/assets/92aed14d-b0ea-48f5-aa0d-740c1bff3870" />

Then I filter for login packets with `tshark -r teamwork.pcap -Y "http contains login.php"` this cam back with the only entry I was looking for.

<img width="1086" height="285" alt="Screenshot 2025-09-08 102841" src="https://github.com/user-attachments/assets/2e4906a6-a3bf-412e-9c37-57f6ccd6bb42" />

Now to expand into the meta data I add `-V` for verbose mode and can find the answer below.

<img width="1067" height="277" alt="Screenshot 2025-09-08 102827" src="https://github.com/user-attachments/assets/06c46353-7bf5-4dd3-ad15-8d31a2a6361c" />

<img width="1272" height="435" alt="Screenshot 2025-09-08 103141" src="https://github.com/user-attachments/assets/9bc85806-157a-4d6d-94fb-3c1ebcdcfde7" />

**40. Investigate the DNS queries. Investigate the domains by using VirusTotal. According to VirusTotal, there is a domain marked as malicious/suspicious. What is the name of the malicious/suspicious domain? Enter your answer in a defanged format.**

First I need a list of DNS queries found so I ran `tshark -r directory-curiosity.pcap -Y "dns.flags.response eq 0" -T fields -e dns.qry.name | sort | uniq`

Then started inputting them into Virus Total and found `jx2-bavuong.com` as the malicous one.

<img width="1805" height="822" alt="Screenshot 2025-09-08 105836" src="https://github.com/user-attachments/assets/a7a70d4d-2ef7-4fa6-8d09-d0ddf6c14f84" />

**41. What is the total number of HTTP requests sent to the malicious domain?**

`tshark -r directory-curiosity.pcap -Y "http.request.full_uri contains jx2" -T fields -e http.request.full_uri | nl`

In this command I am reading the pcap, then using the `http.request.full_uri` display filter and searching for anything conataining jx2, then I only want that field outputted. Then finally | nl to count the lines for me.

<img width="1091" height="493" alt="Screenshot 2025-09-08 110446" src="https://github.com/user-attachments/assets/03d2adbf-398b-46af-8728-a28ec4b1b473" />

**42. What is the IP address associated with the malicious domain?**

Command used: `tshark -r directory-curiosity.pcap -Y "http.host contains jx2" -T fields -e ip.dst -e http.host`

This command reads the pcap, then I am using the http host display filter containing jx2, then the fields I want outputted are the destination ip and host name.

<img width="1078" height="453" alt="Screenshot 2025-09-08 110817" src="https://github.com/user-attachments/assets/5527c36f-6704-42d9-9382-89c2549edb6f" />

**43. What is the server info of the suspicious domain?**

To get this answer I just modify a couple things.

`tshark -r directory-curiosity.pcap -Y "ip.src == 141.164.41.174" -T fields -e http.server`

<img width="1080" height="385" alt="Screenshot 2025-09-08 111454" src="https://github.com/user-attachments/assets/ff4d7d49-0c9c-4e15-b40e-b67511c16ef5" />

**44. Follow the "first TCP stream" in "ASCII". Investigate the output carefully. What is the number of listed files?**

`tshark -r directory-curiosity.pcap -z follow,tcp,ascii,0 -q`

Thios command just follows the TCP stream, within the results I can find the 3 files listed.

<img width="538" height="196" alt="Screenshot 2025-09-08 111743" src="https://github.com/user-attachments/assets/3dd32e6f-983f-4139-aaa7-0e1945589bd0" />

**45. What is the filename of the first file? Enter your answer in a defanged format**

We can see this with the last answer.

**46. Export all HTTP traffic objects. What is the name of the downloaded executable file? Enter your answer in a defanged format.**

I will use a command I used before `tshark -r directory-curiosity.pcap -Y "http.request.uri matches .exe" -T fields -e http.request.uri`

<img width="1069" height="127" alt="Screenshot 2025-09-08 112246" src="https://github.com/user-attachments/assets/03601501-3e1f-4273-818a-221acd2953e5" />

**47. What is the SHA256 value of the malicious file?**

First I need to extract the http objects with `tshark -r directory-curiosity.pcap --export-objects http,/home/ubuntu/Desktop/extracted-by-tshark -q` 

After that I can get the sha256 with `sha256sum vlauto.exe`

<img width="1056" height="68" alt="Screenshot 2025-09-08 112731" src="https://github.com/user-attachments/assets/cc2aedbc-0b41-4b50-b6c9-cbca4b338685" />

**48. Search the SHA256 value of the file on VirtusTotal. What is the "PEiD packer" value?**

Within VirusTotal in the details tab I can find the answer.

<img width="673" height="163" alt="Screenshot 2025-09-08 112832" src="https://github.com/user-attachments/assets/63570e4e-c532-4e60-8747-3fd0886d9c40" />

**49. Search the SHA256 value of the file on VirtusTotal. What does the "Lastline Sandbox" flag this as?**

Within the behavior tab in Virus Total I can see the flags set.

<img width="316" height="642" alt="Screenshot 2025-09-08 113037" src="https://github.com/user-attachments/assets/b21f2d92-86f1-4a94-b3a7-28f1080b74ab" />




















