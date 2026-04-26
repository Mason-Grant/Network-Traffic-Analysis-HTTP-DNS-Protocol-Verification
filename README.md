**1. Objective**

With this project, the aim is to capture and analyse the complete process of a web request. by observing a DNS lookup, TCP handshake and finally HTTP get request conversation, to demonstrate an understanding of the OSI model and the encapsulation of data across a network.

**2. Setup**

Operating system: Parrot Security (running via Oracle Box on a Windows 11 machine)  
Tools: Wireshark GUI and terminal CLI  
Network config: bridged adapter with promiscuous mode enabled  
Target: HTTP://neverssl.com (chosen as the site is unencrypted for good, clear-text analysis)  

**3. Process**
* ***Clear cache*** I cleared cache to prevent my browser from disrupting the capture of a clean DNS query. As parrot is debian-based DNS is not cached and i have not installed a daemon for this so just clearing cache within the browser is sufficient.
* ***Wireshark setup*** Within the parrot CLI i ran 'Sudo Wireshark' to start wireshark. Then i selected eth0 from the list of options as this is my primary interface. I applied a filter to the captured of 'HTTP || DNS' ,to wireshark this HTTP or DNS, to remove unwanted traffic from the list.
* ***Generation of target traffic*** using a browser i navigated to HTTP://networkssl.com in order to generate a DNS lookup and HTTP get request. I had to use the 'nslookup' command as my browser hid the DNS lookup from wireshark.
* ***Analysis*** I discovered the DNS query(UDP port 53). Additionally, using the "Follow TCP stream" function I was able to locate the TCP handshake (SYN,SYN-ACK,ACK) and the HTTP get request conversation in clear-text.


**4. Findings**

**5. Explanation**

**6. Screenshots**
