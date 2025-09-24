# THM-WireShark & Nmap

This will be my process with the Try Hack Me `WireShark: The Basics, WireShark: Packet Operations, and WireShark: Traffic Analysis`

`65 Total questions`


**1. Read the "capture file comments". What is the flag?**

First I go to the `statistics` tab in the top, scroll down to the comments and find the flag.

<img width="414" height="147" alt="Screenshot 2025-08-26 105851" src="https://github.com/user-attachments/assets/8452a145-5e01-44f2-99f3-87314b55c5e6" />

**2. What is the total number of packets?**

In the same tab as the last question, the answer is provided under the `statistics details`

<img width="694" height="205" alt="Screenshot 2025-08-26 105859" src="https://github.com/user-attachments/assets/2ac930b8-5d97-4dc1-a18e-7d556bbfa0d1" />

**3. What is the SHA256 hash value of the capture file?**

Scrolling up in that same details tab, it shows the SHA256 hash

<img width="820" height="230" alt="Screenshot 2025-08-26 110238" src="https://github.com/user-attachments/assets/0234df7c-9921-43d4-8599-1c3e856d263b" />

**4. View packet number 38. Which markup language is used under the HTTP protocol?**

First I select packet 38, then looking at the sections I see Extensible Markup Language below HTTP.

<img width="426" height="200" alt="Screenshot 2025-08-26 111229" src="https://github.com/user-attachments/assets/dbb90c32-f0ee-4626-b844-42476c801936" />

**5. What is the arrival date of the packet? (Answer format: Month/Day/Year)**

In the same packet, I expanded the `frame` tab and saw the answer there.

<img width="804" height="138" alt="Screenshot 2025-08-26 133341" src="https://github.com/user-attachments/assets/c4e1374a-18b0-4574-9799-7aa6d7b8f911" />

**6. What is the TTL value?**

I expanded the `internet protocal` tab and found the answer below.

<img width="868" height="259" alt="Screenshot 2025-08-26 133548" src="https://github.com/user-attachments/assets/9ca95050-84f1-4a00-9317-a0acf3521905" />

**7. What is the TCP payload size?**

First I opened the TCP drop down and scrolled down.

<img width="412" height="116" alt="Screenshot 2025-08-27 094857" src="https://github.com/user-attachments/assets/68f7919d-9b9c-44b3-8b9d-c17415b0b436" />

**8. What is the e-tag value? (For example: 82ecb-6321-9e904585)**

To find this I expanded the HTTP drop down and the answer was there.

<img width="464" height="165" alt="Screenshot 2025-08-27 095445" src="https://github.com/user-attachments/assets/26c18232-e5b5-4e74-9790-d5c06d0ad30a" />

**9. Search the "r4w" string in packet details. What is the name of artist 1?**

First I ctrl + f and search `r4w` then double click the first result. 

<img width="1298" height="101" alt="Screenshot 2025-08-27 104127" src="https://github.com/user-attachments/assets/f223da91-1a07-4b90-b813-893bcf7e578f" />

Then I scrolled through line based text and found the answer there.

<img width="1038" height="247" alt="Screenshot 2025-08-27 104113" src="https://github.com/user-attachments/assets/2d6a1e6e-b057-4686-ad4c-942a25d56878" />

**10. Go to packet 12 and read the packet comments. What is the answer? Note: use md5sum <filename> terminal command to get MD5 hash**

First I go to packet 12 and see there is a comment, taking me somewhere else.

<img width="1118" height="418" alt="Screenshot 2025-08-27 104615" src="https://github.com/user-attachments/assets/656e7be8-58fd-411d-ac11-58b6db179a18" />

Then I went to the packet requested, right clicked the jpeg section, then select export packet bytes.

<img width="378" height="148" alt="Screenshot 2025-08-27 105146" src="https://github.com/user-attachments/assets/d39c299a-7019-4a80-9804-4b35ce9d7040" />

Once I save the file to my desktop, I run the command `md5sum jpeg` to get the md5 hash.

<img width="1060" height="287" alt="Screenshot 2025-08-27 105637" src="https://github.com/user-attachments/assets/85f73b1a-8549-471a-83d3-26d2fc608f4d" />

Then I can open the txt file and see the answer.

<img width="287" height="330" alt="Screenshot 2025-08-27 110034" src="https://github.com/user-attachments/assets/933b9da6-8702-46eb-ae33-05bf82244407" />

<img width="591" height="279" alt="Screenshot 2025-08-27 110206" src="https://github.com/user-attachments/assets/3cde001b-df7f-46b7-8c8e-124a05d97a16" />

<img width="1444" height="223" alt="Screenshot 2025-08-27 110546" src="https://github.com/user-attachments/assets/ede37828-370e-40b3-9361-cfa73ac51fce" />

**11. Look at the expert info section. What is the number of warnings?**

I first go to the analys tab at the top and select Expert information.

<img width="529" height="600" alt="Screenshot 2025-08-27 110911" src="https://github.com/user-attachments/assets/e61ee4c7-630b-45cb-b991-65ee4c055249" />

Then I sleect warnings, and I can see the amount to the right.

<img width="1358" height="119" alt="Screenshot 2025-08-27 111043" src="https://github.com/user-attachments/assets/69379ea1-877f-4153-af2c-101aa6a73d5b" />

**12.Go to packet number 4. Right-click on the "Hypertext Transfer Protocol" and apply it as a filter. Now, look at the filter pane. What is the filter query?**

Right click packet 4and apply it as filter and I see HTTP

<img width="594" height="398" alt="Screenshot 2025-08-27 123151" src="https://github.com/user-attachments/assets/ae379c0f-216b-4141-828c-9f6efc69af5b" />

<img width="202" height="170" alt="Screenshot 2025-08-27 123316" src="https://github.com/user-attachments/assets/81e67b5f-9284-4c3b-b514-3881fe384f56" />

**13. What is the number of displayed packets?**

For this I can see the number at the bottom.

<img width="420" height="41" alt="Screenshot 2025-08-27 123629" src="https://github.com/user-attachments/assets/331d813d-ed48-4597-be72-1a0e6e4e9e41" />

**14. Go to packet number 33790, follow the HTTP stream, and look carefully at the responses. Looking at the web server's response, what is the total number of artists?**

After going to the packet and following the HTTP stream

<img width="1031" height="240" alt="Screenshot 2025-08-27 125643" src="https://github.com/user-attachments/assets/f1e17d79-2ded-4d49-afda-6b9cda031a29" />

I can search for `artist=#` and I see their are no results for artist=4 so I have 3.

<img width="1240" height="226" alt="Screenshot 2025-08-27 125705" src="https://github.com/user-attachments/assets/61493a75-e71d-4126-af76-3b259e32b0ef" />

<img width="1003" height="458" alt="Screenshot 2025-08-27 125718" src="https://github.com/user-attachments/assets/2a59963b-f9b7-4f51-b327-37ff14b1f5c6" />

**15. What is the name of the second artist?**

I can search `artist=2` and find the name next to it.

<img width="1129" height="116" alt="Screenshot 2025-08-27 130027" src="https://github.com/user-attachments/assets/8da3672d-b201-4669-ad68-003a3a59af2a" />

<img width="1089" height="416" alt="Screenshot 2025-08-27 130057" src="https://github.com/user-attachments/assets/215e335c-bd18-4058-97f8-22d232ccdf62" />

**16. Investigate the resolved addresses. What is the IP address of the hostname starts with "bbc"?**

First I selected the statistics tab then look up bbc.

<img width="360" height="116" alt="Screenshot 2025-08-27 150143" src="https://github.com/user-attachments/assets/6d217d6d-bd8b-4e0c-b355-16090297b966" />

<img width="876" height="140" alt="Screenshot 2025-08-27 150210" src="https://github.com/user-attachments/assets/fd0c51ae-7d17-4e9e-95e7-6dcc4bdcdf9c" />

**17. What is the number of IPv4 conversations?**

First in the statistics tab I opened the conversations, and see the iPv4 conversations

<img width="511" height="183" alt="Screenshot 2025-08-27 150331" src="https://github.com/user-attachments/assets/4e97a278-3ed2-402e-899c-1aef85c77987" />

<img width="763" height="117" alt="Screenshot 2025-08-27 150356" src="https://github.com/user-attachments/assets/420487e5-1cae-4fc7-9041-48972852d33b" />

**18. How many bytes (k) were transferred from the "Micro-St" MAC address?**

In the statistics tab I select endpoints, then select name resolution.

<img width="346" height="204" alt="Screenshot 2025-08-27 150916" src="https://github.com/user-attachments/assets/6b2638bf-a2af-4e02-97f5-57bc59fd6fae" />

<img width="677" height="371" alt="Screenshot 2025-08-27 151042" src="https://github.com/user-attachments/assets/045f2175-bfba-4fc4-8190-43d0d78d540f" />

**19. What is the number of IP addresses linked with "Kansas City"?**

In the same endpoints tab I select Ipv4 then sort by city.

<img width="868" height="468" alt="Screenshot 2025-08-27 151256" src="https://github.com/user-attachments/assets/a4407332-8dd0-4efe-9509-335bdbab6218" />

**20. Which IP address is linked with "Blicnet" AS Organisation?**

First thing is I searched the packets for Blicnet, double clicked the packet and saw the destination ip needed.

<img width="1081" height="92" alt="Screenshot 2025-08-27 151713" src="https://github.com/user-attachments/assets/4b1ed581-1202-4d73-bfb7-0b22007dac4d" />

<img width="1015" height="145" alt="Screenshot 2025-08-27 151702" src="https://github.com/user-attachments/assets/b191e3a6-a3f0-4f78-aafa-e8ebda215228" />

**21. What is the most used IPv4 destination address?**

First in the statistics tab, I select ipv4 then all addresses, then filter from most to least.

<img width="529" height="232" alt="Screenshot 2025-08-27 152528" src="https://github.com/user-attachments/assets/3cf24d4a-e48b-42eb-96b6-29229d767151" />

<img width="265" height="116" alt="Screenshot 2025-08-27 152533" src="https://github.com/user-attachments/assets/2f584896-c1b9-4400-b3c5-5d9f91852ac9" />

**22. What is the max service request-response time of the DNS packets?**

First I go to the statistics page and select DNS

<img width="364" height="571" alt="Screenshot 2025-08-27 152959" src="https://github.com/user-attachments/assets/2eafe152-98a2-45c3-9434-7c41782fc98e" />

Then look under the service stats

<img width="784" height="96" alt="Screenshot 2025-08-27 153135" src="https://github.com/user-attachments/assets/58d34f1d-e000-46a2-8370-7a9fbaadbe59" />

**23. What is the number of HTTP Requests accomplished by "rad[.]msn[.]com?**

First in the stats tab select HTTP then requests

<img width="412" height="81" alt="Screenshot 2025-08-27 153824" src="https://github.com/user-attachments/assets/1e6aa26a-5dbb-4857-898d-83b17dde5e49" />

Then find rad.msn.com and go to the right and see the quantity.

<img width="244" height="47" alt="Screenshot 2025-08-27 153801" src="https://github.com/user-attachments/assets/1e49cfb6-2f8b-4e2d-b7a9-e212d567bf89" />

<img width="67" height="66" alt="Screenshot 2025-08-27 153753" src="https://github.com/user-attachments/assets/4f3cde09-b215-4fa3-a71c-e2386a734e18" />

**24. What is the number of IP packets?**

I used the `ip` command and saw the number of displayed packets.

<img width="899" height="729" alt="Screenshot 2025-08-28 085005" src="https://github.com/user-attachments/assets/4b742578-6661-40f5-a509-802fa2ec8e88" />

**25. What is the number of packets with a "TTL value less than 10"?**

I used `ip.ttl < 10`

<img width="810" height="726" alt="Screenshot 2025-08-28 085205" src="https://github.com/user-attachments/assets/012c655c-99ab-4d1f-a470-2fd49984893c" />

**26. What is the number of packets which uses "TCP port 4444"?**

`tcp.port == 4444`

<img width="816" height="728" alt="Screenshot 2025-08-28 085334" src="https://github.com/user-attachments/assets/fce88e39-c13c-40d5-bef4-1d75daa3a55a" />

**27. What is the number of "HTTP GET" requests sent to port "80"?**

`http.request.method == "GET" && tcp.port == 80`

<img width="821" height="736" alt="Screenshot 2025-08-28 085946" src="https://github.com/user-attachments/assets/523229ea-94ff-43b9-8778-6989ae23f899" />

**28. What is the number of "type A DNS Queries"?**

First I start by trying to find a query, I select the analyse tab then Display filter expression.

<img width="346" height="148" alt="Screenshot 2025-08-28 090551" src="https://github.com/user-attachments/assets/6a3541f0-f340-459d-9d93-e0b6ef616a44" />

I searched dns, and scrolled through till I found `dns.qry.type` and this allows me to select only type a.

<img width="825" height="846" alt="Screenshot 2025-08-28 090643" src="https://github.com/user-attachments/assets/2bba545d-288b-4194-8848-f1ab0d64a888" />

This wont give the correct answer, I am needing responses only. So I go back and make another query, by searching dns and scrolling through the options.

I found the one I beleive is correct, it is `dns.flag.response`

<img width="823" height="831" alt="Screenshot 2025-08-28 091159" src="https://github.com/user-attachments/assets/04433b3d-5dac-4ca3-8cef-abd1b9c91fc3" />

Add both together to a full query of `dns.qry.type ==1 && dns.flag.response == 1`

<img width="1505" height="779" alt="Screenshot 2025-08-28 091419" src="https://github.com/user-attachments/assets/c9588386-1cee-4b4a-b3e1-d499b18c40ff" />

**29. Find all Microsoft IIS servers. What is the number of packets that did not originate from "port 80"?**

First I want to find all packets with Microsoft

`http.server contains "Microsoft"`, now that I have all the packets with the Microsoft server, I need a query to find the packets that dont originate from port 80.

full command I used `http.server contains "Microsoft" && tcp.srcport != 80`

<img width="1516" height="768" alt="Screenshot 2025-08-28 094432" src="https://github.com/user-attachments/assets/174d83e8-c0d2-4247-9510-19c8f946a540" />

**30. Find all Microsoft IIS servers. What is the number of packets that have "version 7.5"?**

After looking at the packets and testing queries I landed on this one.

`http.server contains "Microsoft" && http.server matches "7.5"`

<img width="1517" height="780" alt="Screenshot 2025-08-28 095349" src="https://github.com/user-attachments/assets/cfde55bc-0428-4a1f-9370-ef545fad8123" />

**31. What is the total number of packets that use ports 3333, 4444 or 9999?**

`tcp.port in {3333 4444 9999}`

<img width="1512" height="780" alt="Screenshot 2025-08-28 095650" src="https://github.com/user-attachments/assets/cb90370e-10dd-4251-bc6e-d887ae77cb44" />

**32. What is the number of packets with "even TTL numbers"?**

First thing is to translate the packets into strings, this can be done by `string(ip.ttl)`

Then I want the packets to match only even numbers by adding `matches "[02468]$"` this matches only the regex numbers of even numbers, the $ is the anchor saying it needs to end in that even number range.

<img width="1495" height="784" alt="Screenshot 2025-08-28 100511" src="https://github.com/user-attachments/assets/70262306-4749-48ed-bb42-559b57b0d4c0" />

**33. Change the profile to "Checksum Control". What is the number of "Bad TCP Checksum" packets?**

First I select edit, then configuration profiles, then select checksum control.

<img width="366" height="802" alt="Screenshot 2025-08-28 100715" src="https://github.com/user-attachments/assets/f6d305c1-ff63-42dd-b533-3659a0827e3c" />

<img width="861" height="624" alt="Screenshot 2025-08-28 100731" src="https://github.com/user-attachments/assets/97c12604-3f68-4bfe-af99-d04dab3b80fa" />

Then I craft a query by looking up `dns.checksum`

<img width="819" height="782" alt="Screenshot 2025-08-28 100939" src="https://github.com/user-attachments/assets/78bb2ec1-175b-4e89-b3e8-8f0b6e4212df" />

<img width="1381" height="778" alt="Screenshot 2025-08-28 101035" src="https://github.com/user-attachments/assets/ce7d4a63-e830-4a63-ab36-45c5f5f971c5" />

**34. Use the existing filtering button to filter the traffic. What is the number of displayed packets?**

Using the same profile config, use the existing filter gives me the answer.

<img width="963" height="394" alt="Screenshot 2025-08-28 101211" src="https://github.com/user-attachments/assets/47647a99-1f59-4a14-b28f-c06554594c1e" />

<img width="1265" height="470" alt="Screenshot 2025-08-28 101256" src="https://github.com/user-attachments/assets/71138334-5237-4e5d-bbca-6e62e9a521b0" />

# NMAP Notes & Exersises 

**Most common nmap scans:** `TCP connect scans, SYN scans, UDP scans`

**Below are the base filters to probe Nmap scan behaviour on the network:**

Global search - `tcp` `udp`

**TCP Flags**

`tcp.flags == 2` - will only match packets where only the SYN flag is set and no other flags are set. This is typical of the initial SYN packet sent by a client to establish a connection. (SYN flag is the ONLY flag)

`tcp.flags.syn == 1` -  will match any packet where the SYN flag is set, regardless of the state of other flags (e.g., it would match a SYN-ACK packet where both SYN and ACK flags are set).

`tcp.flags == 16` - ACK flag is the only flag

`tcp.flags.ack == 1` - will match any packet with the ACK flag set.

`tcp.flags == 18` - Filters for packets that contain SYN and ACK flags.

`(tcp.flags.syn == 1) and (tcp.flags.ack == 1)` - Second step of the 3 way handshake, filters for packets with ONLY SYN and ACK flags.

`tcp.flags.reset == 1` - Any TCP packet where the RST flag is set to 1. This can include packets with other flags set, such as a RST-ACK packet.

`tcp.flags == 4` - Only TCP packets where only the RST flag is set and all other flags are 0.

`tcp.flags == 20` - Only packets with just the RST and ACK flags set

`(tcp.flags.reset == 1) and (tcp.flags.ack == 1)` - All packets with both the RST and ACK flags set

`tcp.flags.fin == 1` - All packets with the FIN flag set (e.g., FIN and FIN-ACK)

`tcp.flags == 1` - Only packets with just the FIN flag set

**TCP Connect Scan**

Command to test connection and see if port is open `nmap -sT`

`Open TCP Port`(standard tcp handshake) - SYN --> <-- SYN, ACK ACK -->

`Open TCP Port with reset` - SYN --> <-- SYN, ACK ACK --> RST, ACK --> the RST ACK tear down the connection. The RST is a "panic button" that tells the server to immediately close and discard any connection state

`Closed TCP Port` - SYN --> <-- RST, ACK

analysts need to use a generic filter to view the initial anomaly patterns, and then it will be easier to focus on a specific traffic point. The given filter shows the TCP Connect scan patterns in a capture file. - `tcp.flags.syn==1 and tcp.flags.ack==0 and tcp.window_size > 1024`

**SYN Scans**

These dont rely on the 3 way handshake

Usually conducted using `nmap -sS` - this is a stealthier scan than `nmap -sT` it is also quicker and less intrusive.

The handshake is ended before the final ACK packet, this way its stealthier.

`Open TCP Port using -sS` - SYN --> <-- SYN,ACK RST-->

`Close TCP Port using -sS` - SYN --> <-- RST,ACK

The given filter shows the TCP SYN scan patterns in a capture file. - `tcp.flags.syn==1 and tcp.flags.ack==0 and tcp.window_size <= 1024`

**UDP Scan**

ICMP error message for close ports

Doesn't require a handshake process

`Open UDP port` - UDP packet -->

`Closed UDP Port` - UDP packet --> ICMP Type 3, Code 3 message. (Destination unreachable, port unreachable)

The given filter shows the UDP scan patterns in a capture file. - `icmp.type==3 and icmp.code==3`

**35. What is the total number of the "TCP Connect" scans?**

I ran the command I saved for finding all TCP connect scans. `tcp.flags.syn==1 and tcp.flags.ack==0 and tcp.window_size > 1024`

<img width="853" height="736" alt="Screenshot 2025-08-28 121415" src="https://github.com/user-attachments/assets/333031ad-63da-4b8d-95c4-d6756f7184ce" />

**36. Which scan type is used to scan the TCP port 80?**

First I will start by running `tcp.port == 80`

Then once narrowed down I look at the info provided and I can see the normal open port handshake for TCP Connect.

<img width="291" height="98" alt="Screenshot 2025-08-28 122257" src="https://github.com/user-attachments/assets/fc35ed70-b79c-459b-abda-a74c0a21dc77" />

**37. How many "UDP close port" messages are there?**

I ran the search I saved for UDP closed ports - `icmp.type==3 and icmp.code==3`

<img width="845" height="730" alt="Screenshot 2025-08-28 122621" src="https://github.com/user-attachments/assets/185e03ad-47d0-43b9-91ca-3be063f1a29b" />

**38. Which UDP port in the 55-70 port range is open?**

To start I need to find the udp ports in that range, I can do that with this command `udp.port in {55..70}` this searches the udp ports, in the port range described.

<img width="610" height="452" alt="Screenshot 2025-08-28 123006" src="https://github.com/user-attachments/assets/f1b65658-264d-42fc-b790-8e6ebd3b78bb" />

After submitting that query, I can see the ports to the right.

**ARP Poisoning/Spoofing (A.K.A. Man In The Middle Attack)**

ARP protocol, or Address Resolution Protocol (ARP), is the technology responsible for allowing devices to identify themselves on a network. Address Resolution Protocol Poisoning (also known as ARP Spoofing or Man In The Middle (MITM) attack) is a type of attack that involves network jamming/manipulating by sending malicious ARP packets to the default gateway. The ultimate aim is to manipulate the "IP to MAC address table" and sniff the traffic of the target host.

`arp.opcode == 1` - displays all ARP request packets in a captured network trace.

`arp.opcode == 2` - all ARP replies

`arp.dst.hw_mac==00:00:00:00:00:00` - All ARP requests for that MAC 

`arp.duplicate-address-detected or arp.duplicate-address-frame` - This filter flags the initial ARP packet that Wireshark identifies as being part of a duplicate address conflict. Then All subsequent ARP packets that are part of the duplicate IP address conflict.

`((arp) && (arp.opcode == 1)) && (arp.src.hw_mac == target-mac-address)` - find all ARP request packets originating from a specific MAC address.

**39. What is the number of ARP requests crafted by the attacker?**

First command I do is `arp.opcode == 1` to get all ARP request, then I can see that there are a lot of requests to the same address. So I expand the details and note they all have the same MAC. Copy that MAC I will need it later.

Then I run this command to get all request by that MAC. `eth.src == 00:0c:29:e2:18:b4 && arp.opcode ==1`

<img width="861" height="734" alt="Screenshot 2025-08-28 150529" src="https://github.com/user-attachments/assets/4301810e-335b-4cf5-b939-0d2b982b7385" />

**40. What is the number of HTTP packets received by the attacker?**

`eth.dst == 00:0c:29:e2:18:b4 && http`

<img width="788" height="720" alt="Screenshot 2025-08-28 151523" src="https://github.com/user-attachments/assets/ebccb9b6-678e-433e-b90e-a1d2967c040f" />

**41. What is the number of sniffed username&password entries?**

First I want to only see http where data was submitted with a POST. `http.request.method == POST` Then I expanded them and noticed the Hosts were the same.

<img width="340" height="87" alt="Screenshot 2025-08-28 152612" src="https://github.com/user-attachments/assets/79969c9d-8fb5-4dd8-8112-6c91c9e11186" />

I can go through the 10 values and see which ones have usr and psw.

**42. What is the password of the "Client986"**

Since I saw in the last question that the data was captured in the URL Encoder, so I will piggy back off that.

`urlencoded-form matches "client986"`

<img width="500" height="168" alt="Screenshot 2025-08-28 153859" src="https://github.com/user-attachments/assets/4d8e0e47-1324-43a3-87b6-f25e617649a9" />

<img width="576" height="245" alt="Screenshot 2025-08-28 153908" src="https://github.com/user-attachments/assets/15e2f2d0-079c-444c-b090-067b4cc2e407" />

**43. What is the comment provided by the "Client354"?**

Same command as last time, just change the client. `unlencoded-form matches "client354"`

<img width="532" height="146" alt="Screenshot 2025-08-28 154104" src="https://github.com/user-attachments/assets/d07b2f9b-8258-4ee7-a0f0-169a2f2f7125" />

<img width="533" height="216" alt="Screenshot 2025-08-28 154121" src="https://github.com/user-attachments/assets/858ba331-fb46-439c-8cdc-d41abac7ce30" />

**44. What is the MAC address of the host "Galaxy A30"?**

First command I tried was `dhcp.option.hostname contains "Galaxy A30"` but nothing came up, I changed my command to be less exact `dhcp.option.hostname contains "A30"`

That second command was succesful

<img width="845" height="715" alt="Screenshot 2025-09-02 120138" src="https://github.com/user-attachments/assets/279483ba-65ff-468a-ac88-69f7590baaa3" />

**45. How many NetBIOS registration requests does the "LIVALJM" workstation have?**

First I need to craft a search for NBNS registration request filter.

<img width="1265" height="798" alt="Screenshot 2025-09-02 124337" src="https://github.com/user-attachments/assets/186bcbb6-0b0a-4620-b04b-7bb3395bdf38" />

Then I need it to match the name given.

<img width="1262" height="831" alt="Screenshot 2025-09-02 124432" src="https://github.com/user-attachments/assets/d24c3607-d29f-4e84-bbb3-42b53cf80102" />

Then I can see the total at the bottom.

<img width="1629" height="789" alt="Screenshot 2025-09-02 124541" src="https://github.com/user-attachments/assets/a0385310-b8bf-43a5-ab3c-b6849a901cf0" />

**46. Which host requested the IP address "172.16.13.85"?**

First I need just the request flags so I will start with `dhcp.option.dhcp == 3`

Then I go through the filters to find `dhcp.option.request_ip_address == 172.16.13.85`

Final full command I used was `dhcp.option.dhcp == 3 && dhcp.option.request_ip_address == 172.16.13.85`

Then double clicking info to expand to the host.

<img width="1243" height="838" alt="Screenshot 2025-09-02 124857" src="https://github.com/user-attachments/assets/b09bc54b-776c-4f5b-b0c4-6dac748ae353" />

<img width="635" height="300" alt="Screenshot 2025-09-02 125202" src="https://github.com/user-attachments/assets/39ada696-f80b-4335-88be-13f46b09cdff" />

**47. What is the IP address of the user "u5"? (Enter the address in defanged format.)**

First command I used was `kerberos.CNameString contains "u5"` then I double clicked the firsat result and looking into the kerberos details. Found the u5 user and the address associated.

<img width="889" height="390" alt="Screenshot 2025-09-02 125515" src="https://github.com/user-attachments/assets/5c4445a5-8ae8-45c4-bdc2-6e565ae69004" />

<img width="1130" height="323" alt="Screenshot 2025-09-02 125507" src="https://github.com/user-attachments/assets/5df415cd-08d0-4304-8f50-0f9d4b2bb1b6" />

**48. What is the hostname of the available host in the Kerberos packets?** 

I can find this info on the same packet. Just needing to add $ to the end since that indicates hostnames.

<img width="515" height="129" alt="Screenshot 2025-09-02 130038" src="https://github.com/user-attachments/assets/9eff4d67-4f9f-49eb-b540-a30b4268c50d" />

**49. Investigate the anomalous packets. Which protocol is used in ICMP tunnelling?**

The answer to this is one of many protocols used during ICMP tunnelling. I guessed `SSH` since its a popular option.

**50. Investigate the anomalous packets. What is the suspicious main domain address that receives anomalous DNS queries? (Enter the address in defanged format.)**

First I want to look at lond DNS records so I used this command `dns.qry.name.len > 50 and !mdns` I am searching for dns queries that are long entries, which is malicous. Then the !mdns is the multicast local, I am wanting all data other than the local info.

This provided with to many entiries, I need filter more so since I a looking for a domain I can search for anything with ".com"

My full query is `dns.qry.name.len > 50 and !mdns and dns.qry.name contains .com`

Then clicking on one of the entries, you can see the domain to the side.

<img width="1037" height="210" alt="Screenshot 2025-09-02 133719" src="https://github.com/user-attachments/assets/a6c0d726-6a18-4c1a-b9a5-d00339c8600e" />

<img width="1002" height="290" alt="Screenshot 2025-09-02 133710" src="https://github.com/user-attachments/assets/0e698b4f-729a-4f15-84ff-3776df4b123e" />

**51. How many incorrect login attempts are there?**

To get all failed login attempts I need response code of 430 & 530.

`ftp.response.code == 430 and ftp.response.code == 530`

<img width="865" height="713" alt="Screenshot 2025-09-02 141149" src="https://github.com/user-attachments/assets/337ee6ec-e385-4fbc-9037-e58df99e609d" />

**52. What is the size of the file accessed by the "ftp" account?**

This is a user requesting access from the ftp account. So for the command I can use `ftp.request.arg == "ftp"`

Now I have 2 packets, 1 as a PASS and the other is USER ftp, next I will follow the stream of the USER packet.

<img width="773" height="159" alt="Screenshot 2025-09-02 141933" src="https://github.com/user-attachments/assets/7eabd57b-7960-4490-823d-9bfba734dbdd" />

<img width="1008" height="629" alt="Screenshot 2025-09-02 141954" src="https://github.com/user-attachments/assets/e59ec869-50c3-4f43-8e7f-642085704745" />

Scrolling through the TCP stream I can find the answer.

<img width="229" height="98" alt="Screenshot 2025-09-02 142033" src="https://github.com/user-attachments/assets/a3199362-a2ed-450c-ba55-3944660be2eb" />

**53. The adversary uploaded a document to the FTP server. What is the filename?**

Answer is provided in the same place as last question.

**54. The adversary tried to assign special flags to change the executing permissions of the uploaded file. What is the command used by the adversary?**

To find this answer I sorted the packets by latest, then right before the QUIT packet I inspected it and saw they used chmod 777.

<img width="759" height="392" alt="Screenshot 2025-09-02 142828" src="https://github.com/user-attachments/assets/72ed24fe-004c-4a2b-a4d5-9fd637860b36" />

**55. Investigate the user agents. What is the number of anomalous  "user-agent" types?**

First the command I used to see user agents is `http.user_agent` then I added user agent as a column.

<img width="1062" height="735" alt="Screenshot 2025-09-02 144144" src="https://github.com/user-attachments/assets/bc3e7076-329f-42e8-b447-a5f7b39ac979" />

Then I went through the user agent fields and found 6 different entries.

**56. What is the packet number with a subtle spelling difference in the user agent field?**

For this I just looked at the entries or user agent.

<img width="167" height="93" alt="Screenshot 2025-09-02 145026" src="https://github.com/user-attachments/assets/b722eae1-2974-4b36-a016-58e02d9c40b6" />

**57. Locate the "Log4j" attack starting phase. What is the packet number?**

Command I used was `(http.user_agent contains "$") or (http.user_agent contains "==")`

Then I copied the User agent value and decoded from Base 64.

<img width="1448" height="689" alt="Screenshot 2025-09-02 150309" src="https://github.com/user-attachments/assets/b33cd987-1401-44e1-b7e6-5b4920818564" />

<img width="954" height="660" alt="Screenshot 2025-09-02 150316" src="https://github.com/user-attachments/assets/7eacab10-a62e-4e6f-9722-e45f56482c20" />

I can see after it is decoded I can see the wget to get the file lh.sh from the provided IP.

**58. Locate the "Log4j" attack starting phase and decode the base64 command. What is the IP address contacted by the adversary? (Enter the address in defanged format and exclude "{}".)**

Answer provided in the last answer.

**59. What is the frame number of the "Client Hello" message sent to "accounts.google.com"?**

First thing I did was use the command `(http.request or tls.handshake.type == 1) and !(ssdp)` to get all client hello messages. Then clicked on the first entry and found the server name, then selected that as a filter and added "accounts.google.com" and found the answer. Final command with filter is `tls.handshake.extensions_server_name == "accounts.google.com"`

<img width="826" height="700" alt="Screenshot 2025-09-03 113811" src="https://github.com/user-attachments/assets/6ec48406-7cbe-426c-a5bf-7cac5ea27259" />

**60. Decrypt the traffic with the "KeysLogFile.txt" file. What is the number of HTTP2 packets?**

First I add the key log file `Edit > Preferences > Protocols > TLS`

<img width="1051" height="691" alt="Screenshot 2025-09-03 114252" src="https://github.com/user-attachments/assets/df27eb9b-31b3-47a5-bd9b-c3c7a71343ff" />

<img width="706" height="466" alt="Screenshot 2025-09-03 114408" src="https://github.com/user-attachments/assets/5e7630c4-d28d-4f1d-9fc9-40124105e8f2" />

**61. Go to Frame 322. What is the authority header of the HTTP2 packet? (Enter the address in defanged format.)**

First I go to packet 322, then scroll down to the authority header.

<img width="698" height="70" alt="Screenshot 2025-09-03 114541" src="https://github.com/user-attachments/assets/16effc80-230c-449b-8f15-fbe501417a53" />

Then I go to `File > Export Objects > HTTP` I see 2 packets, I will go to the first.

<img width="752" height="724" alt="Screenshot 2025-09-03 114735" src="https://github.com/user-attachments/assets/d2f9f31d-6f17-496c-b26d-eb86491dc789" />

<img width="1055" height="106" alt="Screenshot 2025-09-03 114816" src="https://github.com/user-attachments/assets/ae51800f-13f8-4015-a069-85cc14ab83f7" />

Then scrolling through I can find the flag.

<img width="843" height="329" alt="Screenshot 2025-09-03 114906" src="https://github.com/user-attachments/assets/2900adc8-02e1-4ec5-9a89-fdee112539f4" />

**62. What is the packet number of the credentials using "HTTP Basic Auth"?**

First I go to `Tools > Credentials`

Then I see the answer at the bottom.

<img width="848" height="472" alt="Screenshot 2025-09-03 130306" src="https://github.com/user-attachments/assets/0f65e888-84df-492c-af5a-555f24bf78e7" />

**63. What is the packet number where "empty password" was submitted?**

First I started by filtering for only PASS packets with this command `ftp.request.command == "PASS"`

Then going through each packet I look for an empty passwork field. Below I will show one with a password and the answer with no password.

<img width="502" height="478" alt="Screenshot 2025-09-03 130740" src="https://github.com/user-attachments/assets/35e3af13-99bc-4fcf-82e2-dddaa836e960" />

<img width="854" height="303" alt="Screenshot 2025-09-03 130748" src="https://github.com/user-attachments/assets/a4eddb59-d302-4710-b75f-1a459baa7443" />

<img width="862" height="344" alt="Screenshot 2025-09-03 130730" src="https://github.com/user-attachments/assets/b091edb6-dec7-4526-a51c-5ee0b33ce613" />

**64. Select packet number 99. Create a rule for "IPFirewall (ipfw)". What is the rule for "denying source IPv4 address"?**

<img width="981" height="706" alt="Screenshot 2025-09-03 131127" src="https://github.com/user-attachments/assets/5887e8cf-2d4e-4107-8e76-d3646da6ce02" />

**65. Select packet number 231. Create "IPFirewall" rules. What is the rule for "allowing destination MAC address"?**

<img width="966" height="714" alt="Screenshot 2025-09-03 131320" src="https://github.com/user-attachments/assets/50cabcf1-60aa-4d8d-945a-12b23931e2ad" />

<img width="1207" height="451" alt="Screenshot 2025-09-03 131356" src="https://github.com/user-attachments/assets/cefb30b0-2113-4d1d-b9a5-15fb53af072f" />






























