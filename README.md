**WIRESHARK LABS**  
This repository consists of Week 1 Wireshark Lab Modules Documentation
📌 Project Overview  
This project focuses on completing the 6 labs of Wireshark which is an extra project of Week 1.

**🎯 Objectives**  
The main objectives of this project are to:  
- Learn to detect suspicious activities in the packets.
- Find an attacker's IP Address.
- Become familiar with various protocols.
- Catch the Brute Force Attack.
- Investigate the captured packets, play the audio call and identify the scammer.
- Find usernames and passwords sent in clear text over HTTP.
- Learn the impact of using weak protocols such as HTTP over HTTPS.

**🛡️ Purpose of the Lab**  
The lab provides an isolated and controlled environment for capturing packets and investigating them.

It can be used for activities such as:  
- Capture attacker IP/MAC addresses from SYN scan and port scan traffic  
- Detect SYN flood DoS (tcp.flags.syn == 1 && tcp.flags.ack == 0)   
- Extract cleartext credentials from FTP, HTTP Basic Auth, Telnet

A total of 6 labs were provided and each of them contained 10 tasks.

**⚙️ Lab Results**  
**Identify the Attacker's IP**  
<img width="1080" height="1700" alt="Lab 3 Result - Prakriti Acharya" src="https://github.com/user-attachments/assets/adcd9f2a-9acb-4c31-8513-6469e3f03c79" />

**Summary**  
In short, I learned the following details from this lab:  
- Attacker's IP Address: 192.168.10.66
- Target IP Address: web server 192.168.10.20
- Ports tried: 40 · Open: 22, 80, 443 · Closed: 37 (reply RST, ACK)
- Attack type: Port scan

**Follow TCP Stream 1**  
<img width="1080" height="1700" alt="Lab 4 Result - Prakriti Acharya" src="https://github.com/user-attachments/assets/5f2cc390-959c-4c63-8351-4411eb0a9abb" />

**Summary**  
I found the following details from the second lab:  
- Chat: 192.168.10.45 to server 192.168.10.20, TCP port 5000, stream 5
- Shared in plain text: a temporary password and the guest Wi-Fi password
- Lesson: use encrypted tools (TLS/HTTPS)

**Follow TCP Stream, Part 2**  
<img width="1080" height="1700" alt="Lab 5 Result - Prakriti Acharya" src="https://github.com/user-attachments/assets/d9a0ad36-2363-4bdf-9f05-6902e913e56c" />

**Summary**  
The summary of what I learned in this lab is as follows:  
- Page with the note: /staff.html (stream 7), status 200
- Hidden in an HTML comment: backup server 192.168.10.77, code word Falcon-9921
- File downloaded: report.txt, prepared by Nadia
- Lesson: never leave secrets in web pages

**HTTP Plain Text Credentials**  
<img width="1080" height="1700" alt="Lab 6 Result - Prakriti Acharya" src="https://github.com/user-attachments/assets/e6e7c20f-e7fb-411c-a79b-aec7eb98de4d" />

**Summary**  
In conclusion, I attained the following information through this lab:  
- Protocol: HTTP (not encrypted), method POST to /login
- User farhan.k from 192.168.10.45 tried 2 logins: the first failed, the second worked
- Password sent in plain text: Mango#2026
- Fix: use HTTPS

**Catching Brute Force Attacker**  
<img width="1080" height="1700" alt="Lab 7 Result - Prakriti Acharya" src="https://github.com/user-attachments/assets/7e56e3d7-666e-484c-8be8-f5fd0b6840e5" />

**Summary**  
I was able to gain the following information, in brief, from this lab:  
- Attacker: 192.168.10.66 against FTP server 192.168.10.20 (port 21)
- User admin: 24 failed logins (code 530), then success (code 230) with Sunshine99
- Attack type: brute force
- Fix: lock accounts after a few failures and use strong passwords

**Catching the Call Scammer**  
<img width="1080" height="1700" alt="Lab 8 Result - Prakriti Acharya" src="https://github.com/user-attachments/assets/3590302a-2b88-4151-9735-ad1139ad30a8" />

**Summary**  
This lab, for me, was the most interesting and felt the most accomplishing. I was a bit confused about who made the call and what the caller extension was at first, since applying the filter showed only the caller extension 202. After navigating to the details of the call by double-clicking on the info, I was able to see who the call was from and who it was for. Additionally, I could hear two people actually talking on a call and could gather their card detail, and its expiry date of the card based on the conversation, due to which I felt a wave of accomplishment as well as encouragement to research more on this. Other details of the lab are mentioned below:  
- Call setup: SIP (INVITE, 180 Ringing, 200 OK, ACK, BYE). Voice: RTP, codec G.711 PCMU
- Caller: Ali Raza (extension 101). Answered by: Sara (extension 202)
- Spoken in clear: card number ending 2394, expiry 09/28
- Fix: encrypt calls with SRTP (and use TLS for SIP)

**Conclusion**  
At the end of these 6 labs, I had some understanding of investigating packets, identifying suspicious activities, knowing the attack type, proposing suitable solutions to encrypt sensitive credentials like passwords and card details which are transmitted in plain text more securely, spotting repeated login attempts and finding out who is guessing passwords, and finally, playing the call between people to identify the scammer.
