---
layout: default
title: . 2/4/2022 - Indicators of Compromise Associated with LockBit 2.0 Ransomware 
parent: FBI 
nav_order: 978102799 
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
This is the mobile-friendly web version of the [original article](https://www.ic3.gov/Media/News/2022/220204.pdf).

<img src="https://statics.bsafes.com/images/publications/flash-2022-0204-indicators-of-compromise-associated-with-lockbit-2-0.png" style="display:block; margin:0 auto">

### 4 February 2022
{: .no_toc }
#### Flash Number
{: .no_toc }
### CU-000162-MW 
{: .no_toc }  

1. TOC
{:toc}

The following information is being provided by the FBI, with no guarantees or warranties, for potential use at the sole discretion of recipients in order to protect against cyber threats. This data is provided to help cyber security professionals and system administrators’ guard against the persistent malicious actions of cyber actors. This FLASH was coordinated with DHS-CISA.

This FLASH has been released TLP WHITE. Subject to standard copyright rules, TLP WHITE information may be distributed without restriction.

**WE NEED YOUR HELP!** If you identify any suspicious activity within your enterprise or have related information, please contact your local FBI Cyber Squad immediately with respect to the procedures outlined in the Reporting Notice section of this message.

# Indicators of Compromise Associated with LockBit 2.0 Ransomware    

## Summary
LockBit 2.0 operates as an affiliate-based Ransomware-as-a-Service (RaaS) and employs a wide variety of tactics, techniques, and procedures (TTPs), creating significant challenges for defense and mitigation. LockBit 2.0 ransomware compromises victim networks through a variety of techniques, including, but not limited to, purchased access, unpatched vulnerabilities, insider access, and zero day exploits. 

After compromising a victim network, LockBit 2.0 actors use publicly available tools such as Mimikatz to escalate privileges. The threat actors then use both publicly available and custom tools to exfiltrate data followed by encryption using the Lockbit malware. The actors always leave a ransom note in each affected directory within victim systems, which provides instructions on how to obtain the decryption software. The ransom note also threatens to leak exfiltrated victim data on the LockBit 2.0 leak site and demands a ransom to avoid these actions.

In July 2021, LockBit 2.0 released an update which featured the automatic encryption of devices across windows domains by abusing Active Directory group policies. In August 2021, LockBit 2.0 began to advertise for insiders to establish initial access into potential victim networks, while promising a portion of the proceeds from a successful attack. LockBit 2.0 also developed a Linux-based malware which takes advantage of vulnerabilities within VMWare ESXi virtual machines. 

## Technical Details
LockBit 2.0 is best described as a heavily obfuscated ransomware application leveraging bitwise operations to decode strings and load required modules to evade detection. Upon launch, LockBit 2.0 decodes the necessary strings and code to import the required modules followed by determining if the process has administrative privileges. If privileges are not sufficient, it attempts to escalate to the required privileges. Lockbit 2.0 then determines the system and user language settings and only targets those not matching a set list of languages that are Eastern European. If an Eastern European language is detected, the program exits without infection. As infection begins, Lockbit 2.0 deletes log files and shadow copies residing on disk.  Lockbit 2.0 enumerates system information to include hostname, host configuration, domain information, local drive configuration, remote shares, and mounted external storage devices.  Lockbit 2.0 attempts to encrypt any data saved to any local or remote device but skips files associated with core system functions. Once completed, Lockbit 2.0 deletes itself from disk and creates persistence at startup. 

Prior to encryption, Lockbit affiliates primarily use the Stealbit application obtained directly from the Lockbit panel to exfiltrate specific file types. The desired file types can be configured by the affiliate to tailor the attack to the victim. The affiliate configures the application to target a desired file path and, upon execution, the tool copies the files to an attacker-controlled server using http. Due to the nature of the affiliate model, some attackers use other commercially available tools such as rclone and MEGAsync to achieve the same results. Lockbit 2.0 actors often use publicly available file sharing services including, privatlab[.]net, anonfiles[.]com, sendspace[.]com, fex[.]net, transfer[.]sh, and send.exploit[.]in. While some of these applications and services can support legitimate purposes, they can also be used by threat actors to aid in system compromise or exploration of an enterprise. 


## Indicators
The indicators of compromise (IOCs) and malware characteristics outlined below were derived
from field analysis and the following samples are as of February 2022. 

### *Language check:*

![Figure 1 - Language List](https://statics.bsafes.com/images/publications/flash-2022-0204-indicators-of-compromise-associated-with-lockbit-2-0-fig-1.png)
Figure 1 - Language List

![Figure 2 - Exit Process](https://statics.bsafes.com/images/publications/flash-2022-0204-indicators-of-compromise-associated-with-lockbit-2-0-fig-2.png)
Figure 2 - Exit Process

![Figure 3 - Russian Language](https://statics.bsafes.com/images/publications/flash-2022-0204-indicators-of-compromise-associated-with-lockbit-2-0-fig-3.png)
Figure 3 - Russian Language

### *Command Line Activity:*
The activity below provides a listing of all observed command line activity during execution: 

![](https://statics.bsafes.com/images/publications/flash-2022-0204-indicators-of-compromise-associated-with-lockbit-2-0-cap-2.png)

![](https://statics.bsafes.com/images/publications/flash-2022-0204-indicators-of-compromise-associated-with-lockbit-2-0-cap-3.png)

![](https://statics.bsafes.com/images/publications/flash-2022-0204-indicators-of-compromise-associated-with-lockbit-2-0-cap-4.png)

![](https://statics.bsafes.com/images/publications/flash-2022-0204-indicators-of-compromise-associated-with-lockbit-2-0-cap-5.png)

![](https://statics.bsafes.com/images/publications/flash-2022-0204-indicators-of-compromise-associated-with-lockbit-2-0-cap-6.png)

![](https://statics.bsafes.com/images/publications/flash-2022-0204-indicators-of-compromise-associated-with-lockbit-2-0-cap-7.png)

![](https://statics.bsafes.com/images/publications/flash-2022-0204-indicators-of-compromise-associated-with-lockbit-2-0-cap-8.png)

![](https://statics.bsafes.com/images/publications/flash-2022-0204-indicators-of-compromise-associated-with-lockbit-2-0-cap-9.png)

![Figure 4 - Wallpaper](https://statics.bsafes.com/images/publications/flash-2022-0204-indicators-of-compromise-associated-with-lockbit-2-0-fig-4.png)
Figure 4 - Wallpaper

### *Hidden debug / Status Window:*
Lockbit 2.0 Status / Debug Window is activated when Shift + F1 is pressed. This window is available during the initial infection and provides real time information on process, status of user data destruction and encryption.

![Figure 5 - Screen Capture of Hidden Window](https://statics.bsafes.com/images/publications/flash-2022-0204-indicators-of-compromise-associated-with-lockbit-2-0-fig-5.png)
Figure 5 - Screen Capture of Hidden Window

### Stealbit 
Analysis determined Stealbit is a heavily obfuscated application that uses bitwise operations to build strings and load required modules. The recorded behaviors and characteristics are outlined below, as of February 2022.

Example String decode routine used throughout Lockbit 2.0 and its associated programs:   
IPs are decoded starting with the following bytes which are ANDed by the count stored in ECX. 
![](https://statics.bsafes.com/images/publications/flash-2022-0204-indicators-of-compromise-associated-with-lockbit-2-0-cap-10.png)

![Figure 6 - Encoded IP Address](https://statics.bsafes.com/images/publications/flash-2022-0204-indicators-of-compromise-associated-with-lockbit-2-0-fig-6.png)
Figure 6 - Encoded IP Address

![Figure 7 – Example String Decode Routine, Specifically Used for IPs](https://statics.bsafes.com/images/publications/flash-2022-0204-indicators-of-compromise-associated-with-lockbit-2-0-fig-7.png)
Figure 7 – Example String Decode Routine, Specifically Used for IPs

![](https://statics.bsafes.com/images/publications/flash-2022-0204-indicators-of-compromise-associated-with-lockbit-2-0-cap-11.png)


![Figure 8 – IPs Decoded During Runtime](https://statics.bsafes.com/images/publications/flash-2022-0204-indicators-of-compromise-associated-with-lockbit-2-0-fig-8.png)
Figure 8 – IPs Decoded During Runtime

![](https://statics.bsafes.com/images/publications/flash-2022-0204-indicators-of-compromise-associated-with-lockbit-2-0-cap-12.png)

## Information Requested  

The FBI is seeking any information that can be shared, to include boundary logs showing communication to and from foreign IP addresses, a sample ransom note, communications with the threat actors, Bitcoin wallet information, the decryptor file, and/or a benign sample of an encrypted file. The FBI does not encourage paying ransoms. Payment does not guarantee files will be recovered. It may also embolden adversaries to target additional organizations, encourage other criminal actors to engage in the distribution of ransomware, and/or fund illicit activities. However, the FBI understands that when victims are faced with an inability to function, all options are evaluated to protect shareholders, employees and customers.  Regardless of whether you or your organization have decided to pay the ransom, the FBI urges you to promptly report ransomware incidents to your local field office and/or file a complaint on www.ic3.gov. Doing so provides the FBI with critical information needed to prevent future attacks by identifying and tracking ransomware attackers and holding them accountable under
US law.

***

## Recommended Mitigations:
FBI recommends network defenders apply the following mitigations to reduce the risk of compromise by LockBit 2.0 ransomware: 

- **Require all accounts with password logins (e.g., service account, admin accounts, and domain admin accounts) to have strong, unique passwords**. Passwords should not be reused across multiple accounts or stored on the system where an adversary may have access. Note: Devices with local administrative accounts should implement a password policy that requires strong, unique passwords for each individual administrative account.
- **Require multi-factor authentication** for all services to the extent possible, particularly for webmail, virtual private networks, and accounts that access critical systems.
- **Keep all operating systems and software up to date**. Prioritize patching known exploited vulnerabilities. Timely patching is one of the most efficient and cost-effective steps an organization can take to minimize its exposure to cybersecurity threats.
- **Remove unnecessary access to administrative shares**, especially ADMIN$ and C$. If ADMIN$ and C$ are deemed operationally necessary, restrict privileges to only the necessary service or user accounts and perform continuous monitoring for anomalous activity.
- **Use a host-based firewall** to only allow connections to administrative shares via server message block (SMB) from a limited set of administrator machines.
- **Enable protected files in the Windows Operating System** to prevent unauthorized changes to critical files. 

Adversaries use system and network discovery techniques for network and system visibility and mapping. To limit an adversary from learning the organization’s enterprise environment, limit common system and network discovery techniques by taking the following actions:

- **Segment networks** to prevent the spread of ransomware. Network segmentation can help prevent the spread of ransomware by controlling traffic flows between—and access to—various subnetworks and by restricting adversary lateral movement.
- **Identify, detect, and investigate abnormal activity and potential traversal of the indicated ransomware with a networking monitoring tool**. To aid in detecting the ransomware, implement a tool that logs and reports all network traffic, including lateral movement activity on a network. Endpoint detection and response (EDR) tools are particularly useful for detecting lateral connections as they have insight into common and uncommon network connections for each host. 
- **Implement time-based access for accounts set at the admin level and higher**. For example, the Just-in-Time (JIT) access method provisions privileged access when needed and can support enforcement of the principle of least privilege (as well as the Zero Trust model). This is a process where a network-wide policy is set in place to automatically disable admin accounts at the AD level when the account is not in direct need. When the account is needed, individual users submit their requests through an automated process that enables access to a system, but only for a set timeframe to support task completion.
- **Disable command-line and scripting activities and permissions**. Privilege escalation and lateral movement often depend on software utilities that run from the command line. If threat actors are not able to run these tools, they will have difficulty escalating privileges and/or moving laterally.
- **Maintain offline backups of data**, and regularly maintain backup and restoration. This practice will ensure the organization will not be severely interrupted, have irretrievable data.
- **Ensure all backup data is encrypted, immutable** (i.e., cannot be altered or deleted) and covers the entire organization’s data infrastructure. 

## Additional Resources 
For additional resources related to the prevention and mitigation of ransomware, go to https://www.stopransomware.gov as well as the CISA-Multi-State Information Sharing and Analysis Center (MS-ISAC) Joint Ransomware Guide. Stopransomware.gov is the Government’s official one-stop location for resources to tackle ransomware more effectively.

CISA’s Ransomware Readiness Assessment (RRA) is a no-cost self-assessment based on a tiered set of practices to help organizations better assess how well they are equipped to defend and recover from a ransomware incident.

CISA offers a range of no-cost cyber hygiene services to help critical infrastructure organizations assess, identify, and reduce their exposure to threats, including ransomware. By requesting these services, organizations of any size could find ways to reduce their risk and mitigate attack vectors. 


## Reporting Notice
The FBI encourages recipients of this document to report information concerning suspicious or criminal activity to their local FBI field office. With regards to specific information that appears in this communication; the context, individual indicators, particularly those of a nondeterministic or ephemeral nature (such as filenames or IP addresses), may not be indicative of a compromise. Indicators should always be evaluated in light of your complete information security situation.  

Field office contacts can be identified at www.fbi.gov/contact-us/field-offices. When available, each report submitted should include the date, time, location, type of activity, number of people, type of equipment used for the activity, the name of the submitting company or organization, and a designated point of contact.

## Administrative Note
This product is marked TLP:WHITE. Subject to standard copyright rules, TLP:WHITE information may be distributed without restriction.

<div style="background-color:lightblue; padding:20px" markdown="1">
<h3 style="text-align:center">Your Feedback on the Value of this Product Is Critical</h3>
Was this product of value to your organization? Was the content clear and concise? Your comments are very important to us and can be submitted anonymously. Please take a moment to complete the survey at the link below. Feedback should be specific to your experience with our written products to enable the FBI to make quick and continuous improvements to such products. Feedback may be submitted online here: https://www.ic3.gov/PIFSurvey

Please note that this survey is for feedback on content and value only. Reporting of technical information regarding FLASH reports must be submitted through your FBI Field Office .
</div>
</div>
