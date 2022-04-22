---
layout: default
title: . 4/19/2022 - BlackCat/ALPHV Ransomware Indicators of Compromise  
parent: FBI 
nav_order: 978081299 
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
This is the mobile-friendly web version of the [original article](https://www.ic3.gov/Media/News/2022/220420.pdf).

<img src="https://statics.bsafes.com/images/publications/flash-2022-0419-blackcat-alphv-ransomware-indicators-of-compromise.png" style="display:block; margin:0 auto">

### 19 April 2022
{: .no_toc }
#### Flash Number
{: .no_toc }
### CU-000167-MW 
{: .no_toc }  

1. TOC
{:toc}

The following information is being provided by the FBI, with no guarantees or warranties, for potential use at the sole discretion of recipients in order to protect against cyber threats. This data is provided to help cyber security professionals and system administrators’ guard against the persistent malicious actions of cyber actors. This FLASH was coordinated with DHS-CISA.

This FLASH has been released TLP WHITE. Subject to standard copyright rules, TLP WHITE information may be distributed without restriction.

**WE NEED YOUR HELP!** If you identify any suspicious activity within your enterprise or have related information, please contact your local FBI Cyber Squad immediately with respect to the procedures outlined in the Reporting Notice section of this message.

***

# BlackCat/ALPHV Ransomware Indicators of Compromise    

## Summary
This FLASH is part of a series of FBI reports to disseminate known indicators of compromise (IOCs) and tactics, techniques and procedures (TTPs) associated with ransomware variants identified through FBI investigations. As of March 2022, BlackCat/ALPHV ransomware as a service (RaaS) had compromised at least 60 entities worldwide and is the first ransomware group to do so successfully using RUST, considered to be a more secure programming language that offers improved performance and reliable concurrent processing. BlackCat-affiliated threat actors typically request ransom payments of several million dollars in Bitcoin and Monero but have accepted ransom payments below the initial ransom demand amount. Many of the developers and money launderers for BlackCat/ALPHV are linked to Darkside/Blackmatter, indicating they have extensive networks and experience with ransomware operations.

***

## Technical Details
BlackCat/ALPHV ransomware leverages previously compromised user credentials to gain initial access to the victim system. Once the malware establishes access, it compromises Active Directory user and administrator accounts. The malware uses Windows Task Scheduler to configure malicious Group Policy Objects (GPOs) to deploy ransomware. Initial deployment of the malware leverages PowerShell scripts, in conjunction with Cobalt Strike, and disables security features within the victim’s network.  BlackCat/ALPHV ransomware also leverages Windows administrative tools and Microsoft Sysinternals tools during compromise. 

BlackCat/ALPHV steals victim data prior to the execution of the ransomware, including from cloud providers where company or client data was stored.  

The actors leverage Windows scripting to deploy ransomware and to compromise additional hosts. For example, the following batch and PowerShell scripts were observed:

- start.bat - launches the ransomware executable with required arguments
- est.bat - copies the ransomware to other locations
- drag-and-drop-target.bat - launches the ransomware executable for the MySQL Server
- run.bat - executes a callout command to an external server using SSH - file names may change depending on the company and systems affected
- Runs1.ps1 – PowerShell script to disable McAfee

***

## Indicators
The following are characteristics of compromise by BlackCat/ALPHV, as of mid-February 2022:

![Indicatiors](https://statics.bsafes.com/images/publications/flash-2022-0419-blackcat-alphv-ransomware-indicators-of-compromise-table-1.png)
![Indicatiors](https://statics.bsafes.com/images/publications/flash-2022-0419-blackcat-alphv-ransomware-indicators-of-compromise-table-2.png.png)
![Indicatiors](https://statics.bsafes.com/images/publications/flash-2022-0419-blackcat-alphv-ransomware-indicators-of-compromise-table-3.png.png)


## Information Requested:
The FBI is seeking any information that can be shared, to include IP logs showing callbacks from foreign IP addresses, Bitcoin or Monero addresses and transaction IDs, communications with the threat actors, the decryptor file, and/or a benign sample of an encrypted file.

***

## Recommended Mitigations:

The FBI does not encourage paying ransoms. Payment does not guarantee files will be recovered. It may also embolden adversaries to target additional organizations, encourage other criminal actors to engage in the distribution of ransomware, and/or fund illicit activities. However, the FBI understands that when victims are faced with an inability to function, all options are evaluated to protect shareholders, employees and customers. Regardless of whether you or your organization have decided to pay the ransom, the FBI urges you to promptly report ransomware incidents to your local FBI field office. Doing so provides the FBI with critical information needed to prevent future attacks by identifying and tracking ransomware attackers and holding them accountable under US law.

- Review domain controllers, servers, workstations, and active directories for new or unrecognized user accounts.
- Regularly back up data, air gap, and password protect backup copies offline. Ensure copies of critical data are not accessible for modification or deletion from the system where the data resides.
- Review Task Scheduler for unrecognized scheduled tasks. Additionally, manually review operating system defined or recognized scheduled tasks for unrecognized “actions” (for example: review the steps each scheduled task is expected to perform).
- Review antivirus logs for indications they were unexpectedly turned off.
- Implement network segmentation.
- Require administrator credentials to install software.
- Implement a recovery plan to maintain and retain multiple copies of sensitive or proprietary data and servers in a physically separate, segmented, secure location (e.g., hard drive, storage device, the cloud).
- Install updates/patch operating systems, software, and firmware as soon as updates/patches are released.
- Use multifactor authentication where possible.
- Regularly change passwords to network systems and accounts, and avoid reusing passwords for different accounts.
- Implement the shortest acceptable timeframe for password changes.
- Disable unused remote access/Remote Desktop Protocol (RDP) ports and monitor remote access/RDP logs.
- Audit user accounts with administrative privileges and configure access controls with least privilege in mind.
- Install and regularly update antivirus and anti-malware software on all hosts.
- Only use secure networks and avoid using public Wi-Fi networks. Consider installing and using a virtual private network (VPN).
- Consider adding an email banner to emails received from outside your organization.
- Disable hyperlinks in received emails.  

## Reporting Notice
The FBI encourages recipients of this document to report information concerning suspicious or criminal activity to their local FBI field office. With regards to specific information that appears in this communication; the context, individual indicators, particularly those of a non- deterministic or ephemeral nature (such as filenames or IP addresses), may not be indicative of a compromise. Indicators should always be evaluated in light of your complete information security situation.

Field office contacts can be identified at www.fbi.gov/contact-us/field-offices. When available, each report submitted should include the date, time, location, type of activity, number of people, and type of equipment used for the activity, the name of the submitting company or organization, and a designated point of contact.

## Administrative Note
This product is marked TLP:WHITE. Subject to standard copyright rules, the information in this product may be shared without restriction.

<div style="background-color:lightblue; padding:20px" markdown="1">
<h3 style="text-align:center">Your Feedback on the Value of this Product Is Critical</h3>
Was this product of value to your organization? Was the content clear and concise? Your comments are very important to us and can be submitted anonymously. Please take a moment to complete the survey at the link below. Feedback should be specific to your experience with our written products to enable the FBI to make quick and continuous improvements to such products. Feedback may be submitted online here: https://www.ic3.gov/PIFSurvey

Please note that this survey is for feedback on content and value only. Reporting of technical information regarding FLASH reports must be submitted through your FBI Field Office .
</div>
</div>
