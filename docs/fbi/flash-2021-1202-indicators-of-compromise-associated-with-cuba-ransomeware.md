---
layout: default
title: . 12/2/2021 - Indicators of Compromise Associated with Cuba Ransomware     
parent: FBI 
nav_order: 979002999 
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
This is the mobile-friendly web version of the [original article](https://www.ic3.gov/Media/News/2021/211203-2.pdf).

<img src="https://statics.bsafes.com/images/publications/flash-2021-1202-indicators-of-compromise-associated-with-cuba-ransomeware.png" style="display:block; margin:0 auto">

### 02 Dec 2021
{: .no_toc }
#### Flash Number
{: .no_toc }
### CU-000156-MW 
{: .no_toc }  

1. TOC
{:toc}

The following information is being provided by the FBI, with no guarantees or warranties, for potential use at the sole discretion of recipients in order to protect against cyber threats. This data is provided to help cyber security professionals and system administrators’ guard against the persistent malicious actions of cyber actors. This FLASH was coordinated with DHS-CISA.

This FLASH has been released TLP WHITE. Subject to standard copyright rules, TLP WHITE information may be distributed without restriction.

# Indicators of Compromise Associated with Cuba Ransomware  

## Summary
The FBI has identified, as of early November 2021 that Cuba ransomware actors have compromised at least 49 entities in five critical infrastructure sectors, including but not limited to the financial, government, healthcare, manufacturing, and information technology sectors.  Cuba ransomware is distributed through Hancitor malware, a loader known for dropping or executing stealers, such as Remote Access Trojans (RATs) and other types of ransomware, onto victims’ networks. Hancitor malware actors use phishing emails, Microsoft Exchange vulnerabilities, compromised credentials, or legitimate Remote Desktop Protocol (RDP) tools to gain initial access to a victim’s network. Subsequently, Cuba ransomware actors use legitimate Windows services—such as PowerShell, PsExec, and other unspecified services—and then leverage Windows Admin privileges to execute their ransomware and other processes remotely. Cuba ransomware actors compromise a victim network through the encryption of target files with the “.cuba” extension. Cuba ransomware actors have demanded at least US $74 million and received at least US $43.9 million in ransom payments.

***
<sup>1</sup> A patented router clustering device
{: .fs-2}
***

## Technical Details
Cuba ransomware, upon compromise, installs and executes a CobaltStrike beacon as a service on the victim’s network via PowerShell. Once installed, the ransomware downloads two executable files, which include “pones.exe” for password acquisition and “krots.exe,” also known as KPOT, enabling the Cuba ransomware actors to write to the compromised system’s temporary (TMP) file. Once the TMP file is uploaded, the “krots.exe” file is deleted and the TMP file is executed in the compromised network. The TMP file includes Application Programming Interface (API) calls related to memory injection that, once executed, deletes itself from the system. Upon deletion of the TMP file, the compromised network begins communicating with a reported malware repository located at Montenegro-based Uniform Resource Locator (URL) teoresp.com.
  
Further, Cuba ransomware actors use MimiKatz malware to steal credentials, and then use RDP to log into the compromised network host with a specific user account. Once an RDP connection is complete, the Cuba ransomware actors use the CobaltStrike server to communicate with the compromised user account. One of the initial PowerShell script functions allocates memory space to run a base64-encoded payload. Once this payload is loaded into memory, it can be used to reach the remote command-and-control (C2) server and then deploy the next stage of files for the ransomware. The remote C2 server is located at the malicious URL kurvalarva.com 


## Indicators
The following are characteristics of a Cuba ransomware compromise, as of mid-October 2021: 

![Indicators](https://statics.bsafes.com/images/publications/flash-2021-1202-indicators-of-compromise-associated-with-cuba-ransomeware-table-1.png)

![Indicators](https://statics.bsafes.com/images/publications/flash-2021-1202-indicators-of-compromise-associated-with-cuba-ransomeware-table-2.png)

![Indicators](https://statics.bsafes.com/images/publications/flash-2021-1202-indicators-of-compromise-associated-with-cuba-ransomeware-table-3.png)

![Indicators](https://statics.bsafes.com/images/publications/flash-2021-1202-indicators-of-compromise-associated-with-cuba-ransomeware-table-4.png)

![Indicators](https://statics.bsafes.com/images/publications/flash-2021-1202-indicators-of-compromise-associated-with-cuba-ransomeware-table-5.png)

![Indicators](https://statics.bsafes.com/images/publications/flash-2021-1202-indicators-of-compromise-associated-with-cuba-ransomeware-table-6.png)

![Indicators](https://statics.bsafes.com/images/publications/flash-2021-1202-indicators-of-compromise-associated-with-cuba-ransomeware-table-7.png)

## Information Requested
The FBI is seeking any information that can be shared, to include boundary logs showing communication to and from foreign IP addresses, Bitcoin wallet information, the decryptor file, and/or a benign sample of an encrypted file. The FBI does not encourage paying ransoms.  Payment does not guarantee files will be recovered. It may also embolden adversaries to target additional organizations, encourage other criminal actors to engage in the distribution of ransomware, and/or fund illicit activities. However, the FBI understands that when victims are faced with an inability to function, all options are evaluated to protect shareholders, employees and customers. Regardless of whether you or your organization have decided to pay the ransom, the FBI urges you to promptly report ransomware incidents to your local field office.  Doing so provides the FBI with critical information needed to prevent future attacks by identifying and tracking ransomware attackers and holding them accountable under US law

***

## Recommended Mitigations:
FBI recommends network defenders to apply the following mitigations to reduce the risk of compromise by Cuba ransomware:
- **Require all accounts with password logins (e.g., service account, admin accounts, and
domain admin accounts) to have strong, unique passwords.** Passwords should not be
reused across multiple accounts or stored on the system where an adversary may have
access. Note: Devices with local administrative accounts should implement a password
policy that requires strong, unique passwords for each individual administrative
account.
- **Require multi-factor authentication** for all services to the extent possible, particularly
for webmail, virtual private networks, and accounts that access critical systems.
- **Keep all operating systems and software up to date**. Timely patching is one of the most
efficient and cost-effective steps an organization can take to minimize its exposure to
cybersecurity threats.
- **Remove unnecessary access to administrative shares**, especially ADMIN$ and C$. If
ADMIN$ and C$ are deemed operationally necessary, restrict privileges to only the
necessary service or user accounts and perform continuous monitoring for anomalous
activity.
- **Use a host-based firewall** to only allow connections to administrative shares via server
message block (SMB) from a limited set of administrator machines. 

Adversaries use system and network discovery techniques for network and system visibility and
mapping. To limit an adversary from learning the organization’s enterprise environment, limit
common system and network discovery techniques by taking the following actions: 

- Segment networks to prevent the spread of ransomware. Network segmentation can help prevent the spread of ransomware by controlling traffic flows between—and access to—various subnetworks and by restricting adversary lateral movement.
- Identify, detect, and investigate abnormal activity and potential traversal of the indicated ransomware with a networking monitoring tool. To aid in detecting the ransomware, implement a tool that logs and reports all network traffic, including lateral movement activity on a network. Endpoint detection and response (EDR) tools are particularly useful for detecting lateral connections as they have insight into common and uncommon network connections for each host.
- Implement time-based access for accounts set at the admin level and higher. For example, the Just-in-Time (JIT) access method provisions privileged access when needed and can support enforcement of the principle of least privilege (as well as the Zero Trust model). This is a process where a network-wide policy is set in place to automatically disable admin accounts at the AD level when the account is not in direct need. When the account is needed, individual users submit their requests through an automated process that enables access to a system, but only for a set timeframe to support task completion.
- Disable command-line and scripting activities and permissions. Privilege escalation and lateral movement often depend on software utilities that run from the command line. If threat actors are not able to run these tools, they will have difficulty escalating privileges and/or moving laterally.
- Maintain offline backups of data, and regularly maintain backup and restoration. This practice will ensure the organization will not be severely interrupted, have irretrievable data.
- Ensure all backup data is encrypted, immutable (i.e., cannot be altered or deleted), and covers the entire organization’s data infrastructure.  

## Additional Resources 
For additional resources related to the prevention and mitigation of ransomware, go to https://www.stopransomware.gov as well as the CISA-Multi-State Information Sharing and Analysis Center (MS-ISAC) Joint Ransomware Guide. Stopransomware.gov is the Government’s new, official one-stop location for resources to tackle ransomware more effectively. 
 
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
