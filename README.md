Tools Used
Wireshark – Used for packet capture analysis, protocol inspection, and traffic filtering
NetworkMiner – Used for host identification, basic metadata extraction, os fingerprinting and grab the file in the pcap
IP Geolocation Tool – Used to identify physical locations of IP addresses
PCAP Dataset – Captured HTTP traffic file used for analysis-blob:https://github.com/e6b5e1fc-c8b0-4f3f-8b66-5c52a8ee4fd2

Identified IP Addresses

During the analysis of the PCAP file, the following IP addresses were identified:

65.208.228.223 – External host associated with www.ethereal.com, observed communicating with a Linux-based system.
145.253.2.203 – Internal host (geolocated to Germany).
145.254.160.237 – Internal host grouped with 145.253.2.203, suggesting same network environment.
216.239.59.99 – Google infrastructure, confirmed as legitimate traffic.

Geolocation Analysis

Further geolocation analysis revealed:

145.253.2.203 → Germany
65.208.228.223 → United States

These locations indicate normal distributed web communication between different regions, with no abnormal behavior observed.

External Host Investigation (65.208.228.223)

Since 65.208.228.223 was the most active external host[34 out of 43 papckets]:

Identified as hosting www.ethereal.com
Associated with HTTP communication from a Linux-based system
Confirmed participation in standard web browsing activity

4. User-Agent Analysis

HTTP traffic revealed:

Mozilla/5.0 (Windows NT 5.1; rv:1.6)

Indicates:

Older Windows XP-based system
Standard browser activity

HTTP Method Analysis

Filter used:

http.request.method == "POST"

Results:

No POST requests detected

Findings:

No evidence of data uploads
No login attempts captured
No signs of data exfiltration or command-and-control communication

Traffic Behavior Assessment
Traffic consists mainly of HTTP GET requests
Communication aligns with normal web browsing activity
External services (ethereal.com and Google Ads) appear legitimate
No suspicious payloads or encoded traffic detected

Security Assessment

No Indicators of Compromise (IOCs) were identified:

No suspicious downloads
No POST-based data submission
No command execution patterns
No encoded or obfuscated traffic
No beaconing or abnormal repeated behavior


My Conclusion as SOC Analyst

The analyzed PCAP demonstrates normal HTTP web browsing activity between internal and external hosts. While multiple IP addresses and external services were observed, all traffic patterns align with legitimate network behavior. No evidence of malicious activity, data exfiltration, or attacker behavior was identified during this investigation.
