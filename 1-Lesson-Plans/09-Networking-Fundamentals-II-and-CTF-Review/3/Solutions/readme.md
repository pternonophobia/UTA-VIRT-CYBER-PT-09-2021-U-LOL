##  9.3 Solution Guide: Networking Capture the Flag 

- **Question 11**: The answer to this question required an online search. The answer is found [in this Activision Support article](https://support.activision.com/articles/en_US/FAQ/Ports-Used-for-Call-of-Duty-Games).

- **Question 12**: The total packet count is displayed on the bottom of the Wireshark screen.

- **Question 13**: Adding a filter of ARP will show 19 packets displayed on the bottom of the screen.

- **Question 14**: Filter by HTTP. The first GET request is for the host of thesimpsons.com.

- **Question 15**: Packet number 24 shows the response code of `301 Moved Permanently`.

- **Question 16**: In the same packet in the HTTP details, the redirect goes to fox.com/the-simpsons, the primary domain is fox.com.

- **Question 18**: Packet 23 has the original source port of `50568`.

- **Question 19**: Filter by DNS. In packet 20, in the packet details under **Domain Name Systems** > **Authoritative Nameservers**,  ns01.foxinc.com is shown as the primary nameserver.

- **Question 20**: Filter by DNS. In the DNS response for the A record, packet 19, under Answers, is the TTL of 600.

- **Question 21**: Filter by TCP. There is one SYN > ACK packet, packet 26. Under Timestamps in the packet details is the time since previous frame: 0.026018000.

- **Question 22/23**: These are tricky. The recommended technique is: 
  - Search by "homer."
    - Use a filter `frame contains homer`. 
  - Only one packet displays: packet 46. 
  - This contains the data, but you have the scroll through the packet bytes data to get the answers.

  ![CTFans1](./Images/CTF_ans1.png)

- **Question 24**: In that same packet, the MAC address of Homer, the sender of the message, is `a0:a4:c5:10:ac:c0`. Using any web tool, you will find the vendor is Intel.

- **Question 28**: ASCII of 68 = `h`, 69 = `i`. The answer is `hi`.

- **Question 29/30**: Use the [Browserling Binary to IP translation](https://www.browserling.com/tools/bin-to-ip) web tool. You have to run the conversion three times to get the answer: `38.42.56.32`.

- **Question 31**: Arin.net will provide the AS number for the IP.

- **Question 49**: Using any binary to text converter to will convert the results to `Induction`. The **flag**, however, needs to be lower-case.

- **Question 50**: To decrypt the packets in Wireshark, go to **Edit** > **Preferences**. In the protocols menu, select **IEEE 802.11**.
  
  - Check **Enable decryption**, then select **Edit**, enter in the WPA key of `wpa-pwd` : `Induction`, then filter by HTTP. **Note**: The first `I` in `Induction` is capitalized.  

  ![WPA Key](./Images/CTF_wpa_key.png)

- **Question 51/52**: In packet 439, the packet details have both the values:  `Internet Protocol Version 4, Src: Karens-iMac.local (192.168.0.50), Dst: rr.pmtpa.wikimedia.org (66.230.200.100).`

- **Question 53**: From the top of the toolbar, select **Wireless** > **WLAN traffic**, and the SSID will display.

- **Question 54**: Filter by DNS. The TTL is in packet 429.

- **Question 55**: Filter by ICMP. All responses are unreachable, so the answer is zero.

- **Question 56**: Filter by HTTP. Packet 778 (and several others) has a destination address with the word transcripts, snltranscripts.jt.org. The answer is Saturday Night Live, or snl.

- **Question 58/59**: Packet 2 shows the original (good) MAC that was already assigned, and a new (potentially bad) MAC that it was trying to be changed to.

- **Question 60**: We can see 2015 in the frame part of the packet details of any packet. For example, `Oct  6, 2015 05:28:18.174006000 Eastern Daylight Time.`

- **Question 61**: The formula is n(n -1) / 2 , so (352 * 351) / 2 = 61,776.

- **Question 62**: Number of hosts is 8,192. Subtract the broadcast and network address. Usable hosts: 8,190.

- **Question 63**: For the ARPA, take the IP and switch the order of the octets from last to first. `66.56.54.194` becomes the ARPA IP of `194.54.56.66`.

- **Question 64**: Using an [IPv6 CIDR calculator](https://www.ultratools.com/tools/ipv6CIDRToRange
 ), enter the IPV6 value with the CIDR notation, `2001:db8:85a3::8a2e:370:7334/107`, and it returns the number of hosts: 2,097,152.
