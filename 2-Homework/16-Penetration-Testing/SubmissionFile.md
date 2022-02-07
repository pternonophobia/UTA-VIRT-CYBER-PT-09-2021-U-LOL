## Week 16 Homework Submission File: Penetration Testing 1

#### Step 1: Google Dorking


- Using Google, can you identify who the Chief Executive Officer of Altoro Mutual is: 
  Yes, Karl Fitzgerald, Chairman & Chief Executive Officer of Altoro Mutual

- How can this information be helpful to an attacker:
  This information is very useful to an attacker who wants to send phishing email directly to the executive members.


#### Step 2: DNS and Domain Discovery

Enter the IP address for `demo.testfire.net` into Domain Dossier and answer the following questions based on the results:

  1. Where is the company located: 
  - Sunnyvale, CA, 94085 - USA

  2. What is the NetRange IP address:
  - 65.61.137.64 - 65.61.137.127

  3. What is the company they use to store their infrastructure:
  - Rackspace Backbone Engineering in San Antonio, TX

  4. What is the IP address of the DNS server:
  - 65.61.137.117

#### Step 3: Shodan

- What open ports and running services did Shodan find:
  Open Ports: 80, 443, 8080

#### Step 4: Recon-ng

- Install the Recon module `xssed`. 
- Set the source to `demo.testfire.net`. 
- Run the module. 

Is Altoro Mutual vulnerable to XSS: 
Yes, it was the only vulnerability found.

### Step 5: Zenmap

Your client has asked that you help identify any vulnerabilities with their file-sharing server. Using the Metasploitable machine to act as your client's server, complete the following:

- Command for Zenmap to run a service scan against the Metasploitable machine: 
  nmap -T4 -A 192.168.0.10
 
- Bonus command to output results into a new text file named `zenmapscan.txt`: 
  nmap -T4 -A 192.168.0.10 >> zenmapscan.txt

- Zenmap vulnerability script command: 
  nmap -T4 -F --script ftp-vsftpd-backdoor,smb-enum-shares 192.168.0.10

- Once you have identified this vulnerability, answer the following questions for your client:
  1. What is the vulnerability:
     Zenmap was able to enumerate the vulnerable service

  2. Why is it dangerous:
     This is dangerous due to the VSFTPD 2.3.4 backdoor attack can be applied on port 21 via a malicious code, if successful execution, opens the backdoor on port 6200.

  3. What mitigation strategies can you recommendations for the client to protect their server:
     Update the vsFTPD 2.3.4 patch as soon as possible.

---
© 2020 Trilogy Education Services, a 2U, Inc. brand. All Rights Reserved.  

