a mid-sized financial company received an email appearing to be an overdue invoice notification from a known vendor.

An employee opened the attachment (Excel file) and enabled macros. This triggered a malicious download:

A TrickBot trojan executable was pulled from a compromised WordPress website.

TrickBot quickly beaconed out to a C2 infrastructure over HTTPS (encrypted traffic).

TrickBot then started enumerating internal network shares and exfiltrating credentials.

Within 2 hours, TrickBot prepared the network for Ryuk ransomware deployment, but it was stopped mid-way by an IDS alert.

#🎯 VIP Mission Objectives
Step	Task
1	Identify the exact timestamp when the TrickBot infection started (downloading stage).
2	Find the URL used to deliver the TrickBot payload.
3	Extract the destination C2 IP addresses contacted by TrickBot (hint: unusual HTTPS connections).
4	Calculate the beaconing interval (how often the infected machine communicated with C2).
5	Check if TrickBot attempted lateral movement (any SMB or RDP traffic toward internal IPs).
6	Find evidence of credential theft activity (example: suspicious LDAP, Kerberos, or browser communication).
7	Build a full infection timeline from email open to C2 communication to lateral move attempt.
