# Honeypot Lab
The lab aims to provide interns with practical hands-on experience in analyzing real-world attacks using various enterprise and open-source tools. The focus will be on understanding threat intelligence, tactics, and procedures (TTPs), as well as conducting malware analysis. Interns learn to use tools such as the Elastic stack (Elasticsearch), Splunk Enterprise, CrowdStrike Falcon, as well as online tools such as VirusTotal, ANY.RUN, Hybrid Analysis, and more.
\
\
![7cce81e0c075e6382f7d0d378009a5b3](https://github.com/user-attachments/assets/169e5cac-272f-43c3-80f6-12cb8c2c12c6)
\
\
The honeypot is set up within an EC2 instance on Triangle Cyber's "CyberLab", an AWS provisioned learning environment with restricted privileges to facilitate hands-on learning. The software running on the instance is [T-Pot](https://github.com/telekom-security/tpotce), a honeypot platform that supports multiple individual honeypots on the same server with Elasticsearch support out of the box.
\
\
The chosen honeypots on the server include the following:
* ConPot (ICS honeypot)
* Dionaea (attempts to capture malware binaries)
* Snare / Tanner (vulnerability emulation to lure malicious HTTP requests)
  
\
As well as the following built-in tools:
* T-Pot Attack Map (animated attack map)
* P0f (network fingerprinting)
* Spiderfoot (OSINT tool)
* Suricata (IDS)

\
The honeypot was configured on a completely separate VPC from the rest of the CyberLab, and the firewall rules were locked down to be very restrictive on T-Pot's management ports. The rest of the ports were configured to allow connections from anywhere.
\
\
In addition to the honeypot, a Windows Server 2022 sandbox and a Debian-based sandbox were setup within EC2 instances to facilitate further malware analysis beyond Elasticsearch & Splunk log analysis. CrowdStrike Falcon sensors were installed on the sandboxes, and malware was executed in an extremely restrictive and controlled environment to analyze CrowdStrike Falcon's dynamic analysis capabilities. The sandbox instances utilitized AWS Route 53 and Network Firewall to communicate with the verified Falcon FQDNs while restricting communications to command-and-control (C2) servers.
