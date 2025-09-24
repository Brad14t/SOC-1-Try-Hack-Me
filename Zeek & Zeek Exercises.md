# THM-Zeek & Zeek Exercises
This repo will be my work through of the Try Hack Me module Zeek. This will just be my process of answering the questions, this will not contain all information provided within THM.


**Quick Things to know:**

Default log path - `/opt/zeek/logs/`

Check Zeeks version - `zeek -v`

Check against signature file - `-s`

Their are 2 ways to run Zeek `a service & against a pcap`

ZeekControl - Super user access is required `zeekctl` to manage Zeek.

`zeek-cut` - Cut specific columns from zeek logs.

Zeek Scripts - /opt/zeek/share/zeek/base

# Questions

**What is the installed Zeek instance version number?**

Use command `zeek -v` - `4.2.1`

**What is the version of the ZeekControl module**

Use command `zeekctl` - `2.4.0`

**Investigate the "sample.pcap" file. What is the number of generated alert files**

`zeek -C -r sample.pcap` - this command uses Zeek to read the pcap file, -C is to ignore checksums, -r is for reading the file. Answer is 8 after ls'ing the file and see the 8 new files generated.

<img width="1057" height="138" alt="Screenshot 2025-08-11 130600" src="https://github.com/user-attachments/assets/9589cf5f-3659-4c47-ac05-61960513090f" />

**Investigate the sample.pcap file. Investigate the dhcp.log file. What is the available hostname**

First thing is to read the gicen pcap `zeek -C -r sample.pcap` > After its been read cat out the dhcp file `cat dhcp.log` > Hostname is lited there.

<img width="531" height="309" alt="Screenshot 2025-08-11 131620" src="https://github.com/user-attachments/assets/8fd4df2a-c715-458d-b959-21a7ec3d309e" />

**Investigate the dns.log file. What is the number of unique DNS queries**

First thing is I need to find queries, and remove any duplicates.

To find the answer use command - `cat dns.log | zeek-cut query | sort | uniq`

zeek-cut only picks the queries, sort just sorts them, then uniq removes any duplicates

<img width="1043" height="138" alt="Screenshot 2025-08-11 132516" src="https://github.com/user-attachments/assets/d217654a-1857-470e-aa2f-b7a52f7eaeed" />

**Investigate the conn.log file. What is the longest connection duration**

To find this use `cat conn.log | zeek-cut duration | sort -rn`

I am using zeek-cut for only duration, then sorting from longest to shortest.

<img width="1078" height="136" alt="Screenshot 2025-08-11 132818" src="https://github.com/user-attachments/assets/02b09d02-1380-4962-9f1c-2294eec6c485" />

**Investigate the http.pcap file. Create the  HTTP signature shown in the task and investigate the pcap. What is the source IP of the first event**

First is to go to `/home/ubuntu/Desktop/Exercise-Files/TASK-5/http`

Then I edit the sig file `nano http-password.sig` to match the same one provided.

After I created the rule I will read the pcap. `zeek -C -r http.pcap -s http-password.sig`

After that command 2 files will be generated `signatures.log & notice.log`

To get the first address I used `cat signatures.log | zeek-cut src_addr | sort -r`

This command is showing source addresses and sorting by reverse.

<img width="1054" height="140" alt="Screenshot 2025-08-11 135114" src="https://github.com/user-attachments/assets/c0426e2f-c1f5-4253-8216-efcb8687b761" />

**What is the source port of the second event**

To find this I altered my last command to `cat signatures.log | zeek-cut src_port`

<img width="1068" height="136" alt="Screenshot 2025-08-11 135226" src="https://github.com/user-attachments/assets/80fecfbe-8768-4c1b-9449-8bcd886b63df" />

**Investigate the conn.log. What is the total number of the sent and received packets from source port 38706**

To find this I used `cat conn.log | zeek-cut id.orig_p orig_pkts resp_pkts | grep 38706`

I am reading the conn.log only loking at the originating ip port, and the packets sent back and forth, then grep to search for plain text 38706.

<img width="1062" height="113" alt="Screenshot 2025-08-11 135705" src="https://github.com/user-attachments/assets/97494df3-0648-4684-9cdd-3f45c5097b70" />

Create the global rule shown in the task and investigate the ftp.pcap file.

**Investigate the notice.log. What is the number of unique events**

First thing I did was nano the signature file and matched it to the example given.

<img width="1061" height="287" alt="Screenshot 2025-08-11 140115" src="https://github.com/user-attachments/assets/9b40a8d1-a89a-426b-b30b-193a168b760c" />

After that I use `cat notice.log | zeek-cut uid | sort | uniq | wc -l`

This only uses zeeks uid's, sorts them, makes sure only unique values, then counts the lines. BUT I ran into a problem where any changes I made to the search didnt get me the correct answer. On my deployment after running the command I got 1410. But after some research on the internet, it says the answer is 1413. I am unsure if this is an error on my part or THM, but no matter what I did I always got 1410.

<img width="1065" height="145" alt="Screenshot 2025-08-11 141229" src="https://github.com/user-attachments/assets/30f44936-f060-4fdb-a433-74f02e263132" />

**What is the number of ftp-brute signature matches**

First I adjust to the signatures.log file, the command is slightly altered from the last one.

`cat signatures.log | zeek-cut sig_id | grep "ftp-brute" | wc -l`

<img width="1054" height="89" alt="Screenshot 2025-08-11 141802" src="https://github.com/user-attachments/assets/353bfd23-730c-47e2-b840-184f38323e65" />

**Investigate the smallFlows.pcap file. Investigate the dhcp.log file. What is the domain value of the "vinlap01" host**

First I cd to TASK-6 then I use `zeek -C -r smallflows.pcap`

After that I see the dhcp.log file. To get the domain value I used `cat dhcp.log | zeek-cut domain host_name | grep "vinlap01"`

I ended up not needing host_name.

<img width="1073" height="109" alt="Screenshot 2025-08-11 142914" src="https://github.com/user-attachments/assets/7febaecc-1fa4-45f1-a37d-c81c98f50345" />

**Investigate the bigFlows.pcap file. Investigate the dhcp.log file. What is the number of identified unique hostnames**

First I went to the bigFlows file and read the file using `zeek -C -r bigFlows.pcap` after that the dhcp.log will show.

To get the answer I used `cat dhcp.log | zeek-cut host_name | sort -nr| uniq` then counted the hosts.

<img width="1067" height="534" alt="Screenshot 2025-08-11 143721" src="https://github.com/user-attachments/assets/3a8ddb4a-e0b1-4fcd-993a-13ccc59a179c" />

**Investigate the dhcp.log file. What is the identified domain value**

`cat dhcp.log | zeek-cut domain | uniq`

<img width="1076" height="461" alt="Screenshot 2025-08-11 144009" src="https://github.com/user-attachments/assets/e41adb67-4970-4da1-8194-ed2406a8f745" />

**Go to folder TASK-7/101. Investigate the sample.pcap file with 103.zeek script. Investigate the terminal output. What is the number of the detected new connections**

After going to the correct folder I ran this command: `zeek -C -r sample.pcap 103.zeek | grep "New Connection Found!" | wc -l`

This command reads the pcap using the provided script, then looking for lines containing "New Connection Found!", then counting those lines.

<img width="1069" height="110" alt="Screenshot 2025-08-11 145649" src="https://github.com/user-attachments/assets/d40ac192-a698-4bf2-843a-a8f8982d79db" />

**Go to folder TASK-7/201. Investigate the ftp.pcap file with ftp-admin.sig signature and  201.zeek script. Investigate the signatures.log file. What is the number of signature hits**

After going to the folder I used: `zeek -C -r ftp.pcap 201.zeek -s ftp-admin.sig | wc -l`

<img width="1058" height="103" alt="Screenshot 2025-08-11 150026" src="https://github.com/user-attachments/assets/83893000-c23f-49a1-a9e9-8fe8580200ab" />

**Investigate the signatures.log file. What is the total number of "administrator" username detections**

`cat signatures.log | grep "administrator" | wc -l`

<img width="1080" height="199" alt="Screenshot 2025-08-11 150209" src="https://github.com/user-attachments/assets/3f94e9fe-1bcb-4177-a642-f1d884920793" />

**Investigate the ftp.pcap file with all local scripts, and investigate the loaded_scripts.log file. What is the total number of loaded scripts**

First command will be `zeek -C -r ftp.pcap local`

After that the loaded_scripts.log will be made.

first I tried: `cat loaded_scripts.log | wc -l`, but this gave me an incorrect answer. I noticed some lines were more than 1 so I made sure to grep each command so I can get an accurate number. So to that I changed my command to `cat loaded_scripts.log | grep "/opt/zeek/share" | wc -l`

<img width="1070" height="192" alt="Screenshot 2025-08-11 150509" src="https://github.com/user-attachments/assets/792d56d2-a046-4519-8ff9-d1670fc5c0d2" />

**Go to folder TASK-7/202.
Investigate the ftp-brute.pcap file with "/opt/zeek/share/zeek/policy/protocols/ftp/detect-bruteforcing.zeek" script. Investigate the notice.log file. What is the total number of brute-force detections**

For my command after using the given script I used: `cat notice.log  |zeek-cut note | grep "FTP::Bruteforcing" | wc -l`

I chose this command because if you cat the log file their is a note field that stats Bruteforcing, so that is an easy line to grep.

<img width="1063" height="105" alt="Screenshot 2025-08-11 151353" src="https://github.com/user-attachments/assets/96c6aab6-c6d9-4d2b-875e-d12449eccbf0" />

**Investigate the case1.pcap file with intelligence-demo.zeek script. Investigate the intel.log file. Look at the second finding, where was the intel info found**

First I use the command: `zeek -C -r case1.pcap intelligence-demo.zeek`

Then I read the intel.log file and fins the second finding. Using: `cat intel.log | head`

<img width="530" height="269" alt="Screenshot 2025-08-11 152033" src="https://github.com/user-attachments/assets/3ecfb0ee-420b-4b32-9abb-2579383b2892" />

**Investigate the http.log file. What is the name of the downloaded .exe file**

`cat http.log | zeek-cut uri | grep "\.exe$"`

\.exe$ is searching for exe files, the \. is reex for only dot, and $ signifies the end of the line.

**Investigate the case1.pcap file with hash-demo.zeek script. Investigate the files.log file. What is the MD5 hash of the downloaded .exe file**

First command is `zeek -C -r case1.pcap hash-demo.zeek`

Next is to read the md5 hashes using: `cat files.log | zeek-cut md5`

<img width="1072" height="139" alt="Screenshot 2025-08-11 153557" src="https://github.com/user-attachments/assets/716f3a01-7366-45f1-9695-fd8cf32fc42b" />

**Investigate the case1.pcap file with file-extract-demo.zeek script. Investigate the "extract_files" folder. Review the contents of the text file. What is written in the file**

`zeek -C -r case1.pcap file-extract-demo.zeek`

`file * | nl`

`cat extract-1561667874.743959-HTTP-Fpgan59p6uvNzLFja`

<img width="539" height="232" alt="Screenshot 2025-08-11 154143" src="https://github.com/user-attachments/assets/24ea0395-ecea-4b1c-9ccb-24a0acfa9a73" />

**Investigate the http.pcap file with the zeek-sniffpass module. Investigate the notice.log file. Which username has more module hits**

`cat notice.log | zeek-cut msg` and we can see brozeek has more.

<img width="1073" height="200" alt="Screenshot 2025-08-11 154749" src="https://github.com/user-attachments/assets/8f48bc67-9b9a-4d3a-92f6-5bfcf7543431" />

**Investigate the case2.pcap file with geoip-conn module. Investigate the conn.log file. What is the name of the identified City**

`cat conn.log |zeek-cut id.resp_h geo.resp.city | grep -v -e "-" | uniq -c`

-Chicago

**Which IP address is associated with the identified City**

I can find this info from the last command used.

**Investigate the case2.pcap file with sumstats-counttable.zeek script. How many types of status codes are there in the given traffic capture**

`zeek -C -r case2.pcap sumstats-counttable.zeek` then I can just count the number on the screen.

<img width="1053" height="279" alt="Screenshot 2025-08-11 160103" src="https://github.com/user-attachments/assets/56608a4c-ce85-45bd-b4b6-4fb82a9c4f07" />


<img width="729" height="423" alt="Screenshot 2025-08-11 160217" src="https://github.com/user-attachments/assets/e56f4549-94f4-4920-b7c3-eb44a89e0b55" />

# Zeek Excersises 

**Investigate the dns-tunneling.pcap file. Investigate the dns.log file. What is the number of DNS records linked to the IPv6 address**

To start off I move into the exersise files, I used the command `zeek -C -r dns-tunneling.pcap`

After reading the pcap file, I use the command `cat dns.log` to just take a look and see what the file contains. Inside the file I see a field for qtype_name this will have the record types. To see what records are available I used the command `cat dns.log | zeek-cut qtype_name | uniq` this got me the list of all uniq records, but its just a list and not showing a number of records. After some editing of my command I used `cat dns.log | zeek-cut qtype_name | sort | uniq -c` this will read the dns log, then I am only wanting to look at the record types, then sorting the results, and finally I only want unique entries and I want it to be counted with -c.

<img width="1069" height="513" alt="Screenshot 2025-08-13 103349" src="https://github.com/user-attachments/assets/85915a0c-f5c1-4f1c-8f65-29bfbf81c585" />

I am looking for the AAAA record since this is IPv6 records.

**Investigate the conn.log file. What is the longest connection duration**

First I will use `cat conn.log | head` this will allow me to look for a field I was to use. I see a duration field so I will start with that.

<img width="1069" height="301" alt="Screenshot 2025-08-13 104331" src="https://github.com/user-attachments/assets/622ea35d-7bdf-4e11-9482-260693ea099b" />

First I will try `cat conn.log | zeek-cut duration | sort -nr | head -n 1`, and it worked! This command is me reading the conn log, only looking at the duration field, sorting by numerical in reverse (that way it gives me the longest duration first), then to just have the output look clean I will use head -n 1 so it only shows the top result.

<img width="1047" height="87" alt="Screenshot 2025-08-13 104608" src="https://github.com/user-attachments/assets/3a8e420a-9854-4ae1-a1e6-0fd992a2545c" />

**Investigate the dns.log file. Filter all unique DNS queries. What is the number of unique domain queries?**

First I want to see what the file looks like to I use `cat dns.log | head` then I see lots cisco-update queries. So I will need to use the `cut` command to make the data relevant to the question.

Also looking at the file I need to pick a field to focus on, and for this case I will use query since this is the IP or domain name of the DNS query.

First command I will try is `cat dns.log | zeek-cut query` this was the output.

<img width="693" height="166" alt="Screenshot 2025-08-13 105636" src="https://github.com/user-attachments/assets/3381b961-db9d-4fc0-bcef-5ed3a6b0780e" />

Next I did some testing with the cut command, I landed on `cat dns.log | zeek-cut query | rev | cut -d '.' -f 1-2`| rev` now I have a clean list.

<img width="230" height="110" alt="Screenshot 2025-08-13 110339" src="https://github.com/user-attachments/assets/8ce30452-b32c-4e3f-a095-c549a2d0bb8d" />

Next I will need the number of unique queries, to do this I will add this to the end of my command `| sort | uniq | wc -l` this sorts the list, then only showes unique entries, and finally wc -l counts the lines.

<img width="1072" height="341" alt="Screenshot 2025-08-13 110840" src="https://github.com/user-attachments/assets/e0e876e6-aeec-42c5-b7fc-7ae1bdf522d4" />

**There are a massive amount of DNS queries sent to the same domain. This is abnormal. Let's find out which hosts are involved in this activity. Investigate the conn.log file. What is the IP address of the source host?**

First I look for fields with ` cat conn.log | head` I see the field `id.orig_h` 

My first command will be ` cat conn.log | zeek-cut id.orig_h | sort | uniq` And that gave me the answer.

<img width="1061" height="274" alt="Screenshot 2025-08-13 113110" src="https://github.com/user-attachments/assets/6dc599a2-ddeb-40db-a96e-9c9dfc063131" />

**Investigate the logs. What is the suspicious source address? Enter your answer in defanged format.**

First I will read the pcap with `zeek -C -r phishing.pcap`

Then I will investigate the conn.log since that is all network traffic.

`cat conn.log | head` to find fields. I will use `id.orig_h`

My command will look like `cat conn.log | zeek-cut id.orig_h | sort | uniq`

<img width="1063" height="340" alt="Screenshot 2025-08-13 113709" src="https://github.com/user-attachments/assets/9b6b8f0a-7a2f-481a-85e3-3b82db7c64c4" />

Then to defand add [] around all the .'s

**Investigate the http.log file. Which domain address were the malicious files downloaded from? Enter your answer in defanged format**

First I found the host field to be the best option. So I used `cat http.log | zeek-cut host 

<img width="1059" height="142" alt="Screenshot 2025-08-13 120538" src="https://github.com/user-attachments/assets/280b7d64-1fd9-4991-b881-fd7f4dcfd8bb" />

**Investigate the malicious document in VirusTotal. What kind of file is associated with the malicious document?**

First I need the md5 hash, and to get that I will use a script provided, using `zeek -Cr phishing.pcap hash-demo.zeek`

After running that command I will `cat files.log` I see a field md5 that I will use. I also tried out mime_type and this describes the type of file.

<img width="1066" height="146" alt="Screenshot 2025-08-13 122154" src="https://github.com/user-attachments/assets/df48da1c-94de-4da3-82c4-7ce8674675d7" />

Next I need to find the malicous file, I am going to guess its the third one because I dont recognize it. 

After checking in Virus Total, this seems to not be the file I am looking for. I changed to the second provided md5, and in Virus Total I went to relations, and there is the file type listed.

<img width="941" height="607" alt="Screenshot 2025-08-13 122626" src="https://github.com/user-attachments/assets/486056b6-5818-4575-ac29-65f4afb01418" />

**Investigate the extracted malicious .exe file. What is the given file name in Virustotal?**

To find this I re seearched the md5 of the 3rd file and looked in the details tab, info about the name is provided there.

<img width="1021" height="438" alt="Screenshot 2025-08-13 122951" src="https://github.com/user-attachments/assets/82a24f8e-f420-4f3f-bf40-41a868a4470b" />

**Investigate the malicious .exe file in VirusTotal. What is the contacted domain name? Enter your answer in defanged format.**

To find this I searched through Virus Total and found it in DNS resolves in the behavior tab.

<img width="970" height="302" alt="Screenshot 2025-08-13 123230" src="https://github.com/user-attachments/assets/2eff51bf-1437-49b1-b023-66edc91814dc" />

**Investigate the http.log file. What is the request name of the downloaded malicious .exe file?**

This answer was found nearlier when we ran the command `cat http.log | zeek-cut uri`

**Investigate the log4shell.pcapng file with detection-log4j.zeek script. Investigate the signature.log file. What is the number of signature hits?**

First `zeek -Cr log4shell.pcapng detection-log4j.zeek`

`cat signature.log` and I can see their are 3 hits.

<img width="1070" height="620" alt="Screenshot 2025-08-13 143329" src="https://github.com/user-attachments/assets/89f3326f-3803-4a59-a80f-34d481302bb8" />

**Investigate the http.log file. Which tool is used for scanning?**

`cat http.log` And after running it I can see nmap is being used. 

<img width="1067" height="439" alt="Screenshot 2025-08-13 143606" src="https://github.com/user-attachments/assets/436d4dc2-680f-47d5-a456-50bf95362344" />

**Investigate the http.log file. What is the extension of the exploit file?**

I used the hint here and it says uri info is useful, `cat http.log | zeek-cut uri | sort | uniq

<img width="1077" height="251" alt="Screenshot 2025-08-13 144133" src="https://github.com/user-attachments/assets/6caf51d6-f481-4a06-bda6-622c19a71fa5" />

**Investigate the log4j.log file. Decode the base64 commands. What is the name of the created file?**

First I want to find a fields to cut, so I `cat log4j.log | head` I will use value.

`cat log4j.log | zeek-cut value | grep "Base64"

<img width="1069" height="254" alt="Screenshot 2025-08-13 150001" src="https://github.com/user-attachments/assets/efb94513-0eec-4798-9246-756af9aac82e" />

Then I see copy the lines after /Base64/ and input that into cyber chef.

<img width="655" height="636" alt="Screenshot 2025-08-13 150210" src="https://github.com/user-attachments/assets/bc246d4f-89a8-440f-b216-0fb73ca08424" />

<img width="360" height="487" alt="Screenshot 2025-08-13 150408" src="https://github.com/user-attachments/assets/3a22c032-d107-4c22-aabd-2aaf2c70da69" />





















