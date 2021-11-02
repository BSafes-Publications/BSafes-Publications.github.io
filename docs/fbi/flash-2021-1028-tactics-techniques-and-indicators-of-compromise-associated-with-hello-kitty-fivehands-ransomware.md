---
layout: default
title: . 10/28/2021 - Tactics, Techniques, and Indicators of Compromise Associated with Hello Kitty/FiveHands Ransomware   
parent: FBI 
nav_order: 979020399 
---
<style>
.dont-break-out {
  /* These are technically the same, but use both */
  overflow-wrap: break-word;
  word-wrap: break-word;

  -ms-word-break: break-all;
  /* This is the dangerous one in WebKit, as it breaks things wherever */
  word-break: break-all;
  /* Instead use this non-standard one: */
  word-break: break-word;
}
</style>

<div class="dont-break-out" markdown="1">
This is the mobile-friendly web version of the [original article](https://www.ic3.gov/Media/News/2021/211029.pdf).

<img src="https://statics.bsafes.com/images/publications/flash-2021-1028-tactics-techniques-and-indicators-of-compromise-associated-with-hello-kitty-fivehands-ransomware.png" style="display:block; margin:0 auto">

### 28 Oct 2021
{: .no_toc }
#### Alert Number
{: .no_toc }
### CU-000154-MW 
{: .no_toc }  

1. TOC
{:toc}

The following information is being provided by the FBI, with no guarantees or warranties, for potential use at the sole discretion of recipients in order to protect against cyber threats. This data is provided to help cyber security professionals and system administrators’ guard against the persistent malicious actions of cyber actors. This FLASH was coordinated with DHS-CISA.

This FLASH has been released TLP WHITE. Subject to standard copyright rules, TLP WHITE information may be distributed without restriction.

# Tactics, Techniques, and Indicators of Compromise Associated
with Hello Kitty/FiveHands Ransomware  

## Summary
The FBI first observed Hello Kitty/FiveHands ransomware in January 2021. Hello Kitty/FiveHands actors aggressively apply pressure to victims typically using the double extortion technique. In some cases, if the victim does not respond quickly or does not pay the ransom, the threat actors will launch a Distributed Denial of Service (DDoS) attack on the victim company’s public facing website. Hello Kitty/FiveHands actors demand varying ransom payments in Bitcoin (BTC) that appear tailored to each victim, commensurate with their assessed ability to pay it. If no ransom is paid, the threat actors will post victim data to the Babuk site (payload.bin) or sell it to a third-party data broker. 

## Technical Details
Hello Kitty/FiveHands ransomware uses compromised credentials or known vulnerabilities in SonicWall products (CVE-2021-20016, CVE-2021-20021, CVE-2021- 20022, CVE-2021-20023). Once inside the network, the threat actor will use publicly available penetration tool suites such as Cobalt Strike, Mandiant’s Commando, or PowerShell Empire preloaded with publicly available tools like Bloodhound and Mimikatz to map the network and escalate privileges before exfiltration and encryption. 

## Indicators
The following indicators were leveraged by threat actors during Hello Kitty/FiveHands
ransomware compromises: 

![Indicators](https://statics.bsafes.com/images/publications/flash-2021-1028-tactics-techniques-and-indicators-of-compromise-associated-with-hello-kitty-fivehands-ransomware-fig-1.png)
![Indicators](https://statics.bsafes.com/images/publications/flash-2021-1028-tactics-techniques-and-indicators-of-compromise-associated-with-hello-kitty-fivehands-ransomware-fig-2.png)
![Indicators](https://statics.bsafes.com/images/publications/flash-2021-1028-tactics-techniques-and-indicators-of-compromise-associated-with-hello-kitty-fivehands-ransomware-fig-3.png)
![Indicators](https://statics.bsafes.com/images/publications/flash-2021-1028-tactics-techniques-and-indicators-of-compromise-associated-with-hello-kitty-fivehands-ransomware-fig-4.png)
![Indicators](https://statics.bsafes.com/images/publications/flash-2021-1028-tactics-techniques-and-indicators-of-compromise-associated-with-hello-kitty-fivehands-ransomware-fig-5.png)

## Information Requested
The FBI does not encourage paying a ransom to criminal actors. Paying a ransom may embolden adversaries to target additional organizations, encourage other criminal actors to engage in the distribution of ransomware, or fund illicit activities. Paying the ransom also does not guarantee a victim’s files will be recovered. However, the FBI understands when businesses are faced with an inability to function, executives will evaluate all options to protect their shareholders, employees, and customers. Regardless of whether you or your organization decides to pay the ransom, the FBI urges you to report ransomware incidents to your local field office. Doing so provides investigators and analysts with the critical information they need to track ransomware attackers, hold them accountable under US law, and prevent future attacks.

The FBI may seek the following information:
- Recovered executable files
- Live memory (RAM) capture
- Images of infected systems
- Malware samples
- IP addresses identified as malicious or suspicious
- Email addresses of the attackers
- A copy of the ransom note
- Ransom amount
- Bitcoin wallets used by the attackers
- Bitcoin wallets used to pay the ransom
- Post-incident forensic reports

## Recommended Mitigations:
- Back-up critical data offline.
- Ensure copies of critical data are in the cloud or on an external hard drive or
storage device.
- Secure your back-ups and ensure all data is not accessible for modification or
deletion from the system where the data resides.
- Use two-factor authentication with strong passwords, including for remote access services.
- Monitor cyber threat reporting regarding the publication of compromised VPN login credentials and change passwords and settings, if applicable.
- Keep computers, devices, and applications patched and up-to-date.
- Install and regularly update anti-virus or anti-malware software on all hosts.
- Review the following additional resources:
    - CISA’s analysis report and malware analysis report on FiveHands ransomware provide analysis of a threat actor’s tactics, techniques, and procedures used in a successful cyberattack; indicators of compromise; and recommended mitigations to protect against, detect, and respond to potential FiveHands ransomware attacks.
    - The joint advisory from Australia, Canada, New Zealand, the United Kingdom, and the United States on Technical Approaches to Uncovering and Remediating Malicious Activity provides additional guidance when hunting or investigating a network and common mistakes to avoid in incident handling.
    - The Cybersecurity and Infrastructure Security Agency-Multi-State Information Sharing & Analysis Center Joint Ransomware Guide covers additional best practices and ways to prevent, protect, and respond to a ransomware attack.
    - StopRansomware.gov is the US Government’s official one-stop location for resources to tackle ransomware more effectively.

If your organization is impacted by a ransomware incident, the FBI and CISA recommend the following actions:

- Isolate the infected system. Remove the infected system from all networks, and disable the computer’s networking capabilities, including wireless and Bluetooth. Ensure all shared and networked drives are disconnected, whether wired or wireless.
- Turn off other computers and devices. Power-off and segregate (i.e., remove from the network) the infected computer(s). Power-off and segregate any additional computers or devices that share a network with the infected computer(s), even if they have not been fully encrypted by ransomware. If possible, collect and secure all infected and potentially infected computers and devices in a central location, making sure to clearly label any computers that have been encrypted. Powering-off and segregating infected computers and computers that have not been fully encrypted may allow for the recovery of partially encrypted files by specialists.
- Secure your backups. Ensure that your backup data is offline and secured. If possible, scan your backup data with an antivirus program to check that it is free of malware.

## Reporting Notice
The FBI encourages recipients of this document to report information concerning suspicious or criminal activity to their local FBI field office. With regards to specific information that appears in this communication; the context, individual indicators, particularly those of a nondeterministic or ephemeral nature (such as filenames or IP addresses), may not be indicative of a compromise. Indicators should always be evaluated in light of your complete information security situation.  

Field office contacts can be identified at www.fbi.gov/contact-us/field-offices. When available, each report submitted should include the date, time, location, type of activity, number of people, type of equipment used for the activity, the name of the submitting company or organization, and a designated point of contact.

## Administrative Note
This product is marked TLP:WHITE. Subject to standard copyright rules, TLP:WHITE information may be distributed without restriction.

For comments or questions related to the content or dissemination of this product, contact CyWatch.

<div style="background-color:lightblue; padding:20px" markdown="1">
<h3 style="text-align:center">Your Feedback on the Value of this Product Is Critical</h3>
Was this product of value to your organization? Was the content clear and concise? Your comments are very important to us and can be submitted anonymously. Please take a moment to complete the survey at the link below. Feedback should be specific to your experience with our written products to enable the FBI to make quick and continuous improvements to such products. Feedback may be submitted online here: https://www.ic3.gov/PIFSurvey

Please note that this survey is for feedback on content and value only. Reporting of technical information regarding FLASH reports must be submitted through your FBI Field Office .
</div>
</div>
