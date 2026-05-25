 Email Header Analysis project focused on phishing and cybersecurity threat detection.
The analysis examines multiple Microsoft Office 365 phishing email headers and identifies common attack patterns such as spoofed sender addresses, failed SPF/DKIM/DMARC authentication, suspicious Reply-To hijacking, attacker-controlled domains, and repeated sender infrastructure from the 89.144.x.x IP range.

This project helps to  understand how email headers reveal phishing behavior, how relay chains expose suspicious infrastructure, and how security teams can use technical indicators to improve detection and prevention.

Key areas covered:

Email header forensic analysis
SPF, DKIM, and DMARC validation
Sender spoofing detection
Reply-To hijacking investigation
Office 365 anti-spam indicators
Relay-chain and IP reputation analysis
Security recommendations for phishing defense

Key Findings:

1. Sender Spoofing
The emails use a misleading display name:Microsoft account team
However, the actual sender address is attacker-controlled: no-reply@access-accsecurity.com
This is a common phishing technique used to make the email appear legitimate to the recipient.

2. Authentication Failures
The analyzed samples show repeated email authentication failures:
SPF: none
DKIM: none
DMARC: permerror

These failures indicate that the sending domains are not properly authorized and that the messages should be treated as suspicious.

3. Reply-To Hijacking
The emails contain attacker-controlled Reply-To addresses such as
sotrecognizd@gmail.com
solutionteamrecognizd02@gmail.com
solutionteamrecognizd03@gmail.com

This allows attackers to receive victim replies even if the visible sender appears to be Microsoft-related.

4. Suspicious Sender Infrastructure
Several emails originate from IP addresses in the 89.144.x.x range, including:
89.144.44.2
89.144.44.4
89.144.9.87
89.144.9.91
   The repeated use of this IP range suggests coordinated phishing infrastructure or reused attacker-controlled servers.

5. Microsoft Exchange Anti-Spam Indicators
The headers include Microsoft Exchange spam confidence indicators such as:
X-MS-Exchange-Organization-SCL: 5
X-Microsoft-Antispam: BCL:6
X-MS-Exchange-Organization-SCL: 5
X-Microsoft-Antispam: BCL:6

Important Header Fields Analyzed

From:	Checks visible sender identity
Reply-To:	Identifies where replies are redirected
Return-Path:	Shows actual bounce/sender domain
Received:	Tracks mail relay path
Authentication-Results:	Shows SPF, DKIM, and DMARC results
X-Sender-IP:	Identifies originating IP address
X-MS-Exchange-Organization-SCL:	Microsoft spam confidence level
X-Microsoft-Antispam:	Microsoft anti-spam classification data

Threat Indicators
The following indicators were observed across the samples:

Spoofed Microsoft account team sender
Failed SPF validation
Missing DKIM signature
DMARC permanent error
Suspicious Reply-To Gmail accounts
Non-Microsoft sending domains
Repeated attacker IP range
High-priority phishing email headers
Microsoft Office 365 targeting pattern
Security Recommendations
Organizations should consider the following defensive measures:

Enforce strict DMARC policies using quarantine or reject
Monitor SPF, DKIM, and DMARC failures
Block or investigate suspicious IP ranges
Detect mismatches between From, Reply-To, and Return-Path
Add external sender warnings for inbound emails
Train users to identify spoofed Microsoft account emails
Monitor Microsoft Exchange SCL and BCL values
Create mail flow rules for suspicious Reply-To behavior
Conclusion
This project demonstrates how email headers can reveal strong evidence of phishing activity. Even when an email appears to come from a trusted brand, technical header analysis can expose spoofing, authentication failure, suspicious relay paths, and attacker-controlled reply addresses.

Email header analysis is an important skill in cybersecurity, digital forensics, phishing investigation, and SOC operations.

Skills Demonstrated
Email header analysis
Phishing detection
Cybersecurity investigation
SPF, DKIM, and DMARC analysis
Threat indicator identification
Microsoft Exchange header interpretation
Security reporting
