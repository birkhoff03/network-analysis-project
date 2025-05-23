# Security Incident Investigation: Uncovering a Hidden Attack on an Endpoint


John M., Head of Endpoint Security at our Silicon Valley headquarters, flew to the invite-only Global BYOD Security Forum 2025 in Berlin—a gathering of top security leaders from Fortune 500 companies. While there, he attended a private demo of next-gen Mobile Device Management (MDM) software on the event’s secure guest network.

Three days after returning, our SOC noticed encrypted outbound signals from John’s MacBook to unregistered IPs in Moldova. No logs, no alerts—just raw network traffic quietly captured by a silent NetFlow sensor at our network edge.

John dismissed it as “maybe Zoom telemetry,” but Pete Galloway—our lead malware reverse engineer—wasn’t convinced.

Pete retrieved the full packet capture from our endpoint forensic archive. Hidden inside a seemingly normal HTTP response was something unusual: a binary blob disguised as a favicon.ico file containing compiled Python bytecode.

Pete knew this was no ordinary artifact. He stayed late, dissecting the payload, decoding strings, XOR keys, and memory injections.

At 2:36 a.m., he committed his last note to our internal Git repo:

> "# this isn’t automation. this was meant for John. whoever did this... they knew him."

The next morning, Pete didn’t show up.

At 8:17 a.m., an internal email was sent from his laptop:

- Subject: [None]  
- Body: “Fuck you. I quit.”  

The message was signed with his private GPG key.

We’re now holding a `.pcapng` file, a partially decompiled payload, and no sign of Pete.

John left again this morning for the Honeynet Project Workshop in Stavanger, but we’ve grounded all travel and isolated his laptop.

This wasn’t an accident. It was a message.

## Your Mission

- Analyze the provided `.pcapng` file and forensic artifacts.  
- Reconstruct what happened step-by-step.  
- Identify the nature of the payload and its purpose.  
- Find any clues related to Pete’s disappearance and the attack’s origin.  
- Document your findings and submit your analysis.

## Prerequisites

- Familiarity with network traffic analysis tools (e.g., Wireshark, tcpdump).  
- Experience with reverse engineering (especially Python bytecode).  
- Basic understanding of malware analysis techniques.  
- Knowledge of cryptography concepts (XOR keys, GPG signatures).  

## Tools & Resources

- Wireshark or any PCAP analyzer  
- Python disassembler/decompiler (e.g., uncompyle6, pycdc)  
- Hex editors and memory analysis tools  
- GPG key verification tools  

## Getting Started

1. Download the provided `.pcapng` capture file from the repo.  
2. Inspect network traffic for unusual activity and hidden payloads.  
3. Extract and analyze the suspicious favicon.ico binary blob.  
4. Reverse engineer the Python bytecode to understand its function.  
5. Cross-reference findings with Pete’s Git commits and emails.  

## Contributing

Feel free to submit pull requests with your analysis, scripts, or tools that help with the investigation. Discussions and hints are welcome in the Issues section.
