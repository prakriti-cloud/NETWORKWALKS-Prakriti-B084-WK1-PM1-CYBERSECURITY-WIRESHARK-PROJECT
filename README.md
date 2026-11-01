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
<img width="959" height="434" alt="Screenshot 2026-11-01 191654" src="https://github.com/user-attachments/assets/f48ea4f4-2688-4cb0-bdd7-ef043886120a" />


**Summary**  
In short, I learned the following details from this lab:  
- Attacker's IP Address: 192.168.10.66
- Target IP Address: web server 192.168.10.20
- Ports tried: 40 · Open: 22, 80, 443 · Closed: 37 (reply RST, ACK)
- Attack type: Port scan

**Follow TCP Stream 1**  
<img width="956" height="445" alt="Screenshot 2026-11-01 192016" src="https://github.com/user-attachments/assets/65d68996-580d-4b24-b97d-ae0a99857610" />


**Summary**  
I found the following details from the second lab:  
- Chat: 192.168.10.45 to server 192.168.10.20, TCP port 5000, stream 5
- Shared in plain text: a temporary password and the guest Wi-Fi password
- Lesson: use encrypted tools (TLS/HTTPS)

**Follow TCP Stream, Part 2**  
<img width="951" height="433" alt="Screenshot 2026-11-01 192232" src="https://github.com/user-attachments/assets/6527a9f8-5313-474d-bf84-0677d22e57f5" />


**Summary**  
The summary of what I learned in this lab is as follows:  
- Page with the note: /staff.html (stream 7), status 200
- Hidden in an HTML comment: backup server 192.168.10.77, code word Falcon-9921
- File downloaded: report.txt, prepared by Nadia
- Lesson: never leave secrets in web pages

**HTTP Plain Text Credentials**  
<img width="950" height="439" alt="Screenshot 2026-11-01 192500" src="https://github.com/user-attachments/assets/62b8161c-9029-4d12-b005-06f034453460" />


**Summary**  
In conclusion, I attained the following information through this lab:  
- Protocol: HTTP (not encrypted), method POST to /login
- User farhan.k from 192.168.10.45 tried 2 logins: the first failed, the second worked
- Password sent in plain text: Mango#2026
- Fix: use HTTPS

**Catching Brute Force Attacker**  
<img width="956" height="435" alt="Screenshot 2026-11-01 192921" src="https://github.com/user-attachments/assets/d428e144-7f48-41eb-b6ba-6e9da2d66997" />


**Summary**  
I was able to gain the following information, in brief, from this lab:  
- Attacker: 192.168.10.66 against FTP server 192.168.10.20 (port 21)
- User admin: 24 failed logins (code 530), then success (code 230) with Sunshine99
- Attack type: brute force
- Fix: lock accounts after a few failures and use strong passwords

**Catching the Call Scammer**  
<img width="949" height="440" alt="Screenshot 2026-11-01 193158" src="https://github.com/user-attachments/assets/f9c21454-1ee8-45e3-bd71-cabaad6f627e" />


**Summary**  
This lab, for me, was the most interesting and felt the most accomplishing. I was a bit confused about who made the call and what the caller extension was at first, since applying the filter showed only the caller extension 202. After navigating to the details of the call by double-clicking on the info, I was able to see who the call was from and who it was for. Additionally, I could hear two people actually talking on a call and could gather their card detail, and its expiry date of the card based on the conversation, due to which I felt a wave of accomplishment as well as encouragement to research more on this. Other details of the lab are mentioned below:  
- Call setup: SIP (INVITE, 180 Ringing, 200 OK, ACK, BYE). Voice: RTP, codec G.711 PCMU
- Caller: Ali Raza (extension 101). Answered by: Sara (extension 202)
- Spoken in clear: card number ending 2394, expiry 09/28
- Fix: encrypt calls with SRTP (and use TLS for SIP)

**Conclusion**  
At the end of these 6 labs, I had some understanding of investigating packets, identifying suspicious activities, knowing the attack type, proposing suitable solutions to encrypt sensitive credentials like passwords and card details which are transmitted in plain text more securely, spotting repeated login attempts and finding out who is guessing passwords, and finally, playing the call between people to identify the scammer.
