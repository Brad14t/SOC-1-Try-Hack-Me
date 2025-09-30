# SOC-Alert-8816

`Alert:` Access to Blacklisted External URL blocked by firewall.

First I will read over the information provided.

<img width="1444" height="807" alt="Screenshot 2025-09-30 095052" src="https://github.com/user-attachments/assets/fe3eaa56-a591-410d-a462-9cb4a41f2d2d" />

I'll edit the timeline to right before the alert.

<img width="966" height="214" alt="Screenshot 2025-09-30 095231" src="https://github.com/user-attachments/assets/77f3310b-8c8d-4a10-808a-b8b8efd5e01f" />

Next I will query the url given to see if this link was sent to anyone else. `index=* "*http://bit.ly/3sHkX3da12340*"`

I get 2 results.

Next I will see if the source IP sent anything else. `index=* SourceIP=10.20.2.17`

I get 2 results but the 1st one isnt malicous.

Then I'll see if anything else was sent to the destination IP 67.199.248.11.

`index=* DestinationIP=67.199.248.11`

Only the 1 result. Now I will see if anything was sent from 67.199.248.11. And found nothing

Next I looked up the URL provided, and nothing comes back as malicous.

<img width="973" height="397" alt="Screenshot 2025-09-30 101124" src="https://github.com/user-attachments/assets/dfe6401c-b25d-4a6c-9e9a-f7a26aedfc9d" />

<img width="1196" height="602" alt="Screenshot 2025-09-30 101950" src="https://github.com/user-attachments/assets/163711b8-3496-4ddc-8543-0b779f48244c" />

I also looked up the source IP, and nothing shows as malicous.

<img width="976" height="401" alt="Screenshot 2025-09-30 102348" src="https://github.com/user-attachments/assets/cfa4ffeb-7e37-4e0f-9ad6-5760a3b06533" />

<img width="1192" height="771" alt="Screenshot 2025-09-30 102453" src="https://github.com/user-attachments/assets/c97dd7ec-02bd-4201-9011-2a3583ef98fe" />

Next I will use the internal tools, I open the Analyst VM and open Try Detect This. I ran the URL and IP's provided.

<img width="1310" height="544" alt="Screenshot 2025-09-30 102928" src="https://github.com/user-attachments/assets/7ca594db-0bbe-4f45-8f1b-503728532fc0" />

<img width="1319" height="575" alt="Screenshot 2025-09-30 102951" src="https://github.com/user-attachments/assets/26eccbac-3964-4f2e-9052-bd5d76cf4697" />

<img width="1218" height="594" alt="Screenshot 2025-09-30 103115" src="https://github.com/user-attachments/assets/a7c70c66-2f3b-40c9-bb13-fe1d220bc6d1" />

This proves that the link was indead malicous, and the destination IP is also detected as malicous.

I will write up my case report now.

<img width="1424" height="899" alt="Screenshot 2025-09-30 103643" src="https://github.com/user-attachments/assets/07f3d3e8-9ba7-4274-a61b-d3168b8174aa" />









