---
layout: default
title: . 10/25/2021 - Indicators of Compromise Associated with Ranzy Locker Ransomware  
parent: FBI 
nav_order: 979020699 
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
This is the mobile-friendly web version of the [original article](https://www.ic3.gov/Media/News/2021/211026.pdf).

<img src="https://statics.bsafes.com/images/publications/flash-2021-1025-indicatiors-of-compormise-associated-with-ranzy-locker-ransomeware.png" alt="Indicators of Compromise Associated with Hive Ransomware" style="display:block; margin:0 auto">

### 25 Oct 2021
{: .no_toc }
#### Alert Number
{: .no_toc }
###  MC-000150-MW
{: .no_toc }  

1. TOC
{:toc}

The following information is being provided by the FBI, with no guarantees or warranties, for potential use at the sole discretion of recipients in order to protect against cyber threats. This data is provided to help cyber security professionals and system administrators’ guard against the persistent malicious actions of cyber actors. This FLASH was coordinated with DHS-CISA.

This FLASH has been released TLP WHITE. Subject to standard copyright rules, TLP WHITE information may be distributed without restriction.

# Indicators of Compromise Associated with Ranzy Locker Ransomware 

## Summary
The FBI first identified Ranzy Locker ransomware in late 2020 when the variant began to target victims in the United States. Unknown cyber criminals using Ranzy Locker ransomware had compromised more than 30 US businesses as of July 2021. The victims include the construction subsector of the critical manufacturing sector, the academia subsector of the government facilities sector, the information technology sector, and the transportation sector. 

A majority of victims reported the actors conducted a brute force attack targeting Remote Desktop Protocol (RDP) credentials to gain access to the victims’ networks. Recent victims reported the actors leveraged known Microsoft Exchange Server vulnerabilities and phishing as the means of compromising their networks. The actors attempted to locate important files to exfiltrate, such as customer information, PII related files, and financial records. Ranzy Locker is deployed to encrypt files on compromised Windows host systems (including servers and virtual machines) and attached network shares. The Ranzy Locker executable leaves a ransom note in all directories where encryption occurred demanding the victim pay a ransom in exchange for a decryption tool. In an example of double extortion techniques, Ranzy actors in some cases have demanded a second ransom from the victim in exchange for not leaking the data on the Internet.

## Technical Details and Indicators
The FBI identified the following indicators of compromise (IOCs) that we assess are likely associated with Ranzy Locker activity.

### **New User Accounts**
The Ranzy Locker actors may establish new accounts on domain controllers, servers, workstations, or the active directories. Newly created accounts with the name “felix” have been observed on at least three victims of the ransomware. 

### **Ransom Note**
The ransom note for Ranzy Locker has similarities to the wording in both the AKO and ThunderX ransom notes.<sup>1</sup> An example of the notes is below:

![Ransom Note](https://statics.bsafes.com/images/publications/flash-2021-1025-indicatiors-of-compormise-associated-with-ranzy-locker-ransomeware-fig-1.png)

The key found in the ransom note is a base64 encoded string, which when decoded reads:
    {"ext":".ranzy","network":"true/false","subID":"####","lang":"xx-XX."}

***
<sup>1</sup>Around October 2020 both AKO and ThunderX rebranded themselves as Ranzy Locker Ransomware.
{: .fs-2}
***

The .ext extension parameter is typically .ranzy for Ranzy Locker 1.1, and the network parameter is typically set to true. The lang parameter is the language of the computer, such as “en-US.”

The subID parameter is an integer and is the name of the Ranzy Locker executable on the
system. For example, if the subid is 0000, then the Ranzy Locker executable’s name is 0000.exe.

### **Ransomware Executable**
The name of the Ranzy Locker executable is the subID found in the key on the ransom note. It is a 32-bit portable executable (PE), and all samples observed on different victims have different hash values but identical functionality. The executable requires administrator credentials to run.

Each Ranzy Locker executable contains the same hex encoded strings. Some of these strings are commands used to delete any backups on the system. The table below has the hex string, decoded string, and explanation of the string (if known):

![Ransomware Executable](https://statics.bsafes.com/images/publications/flash-2021-1025-indicatiors-of-compormise-associated-with-ranzy-locker-ransomeware-fig-2.png)

![Ransomware Executable](https://statics.bsafes.com/images/publications/flash-2021-1025-indicatiors-of-compormise-associated-with-ranzy-locker-ransomeware-fig-3.png)

As these hex strings are present in all Ranzy Locker samples, they provide points for detection such as with YARA. A sample YARA rule can be found here:
https://www.tutorialjinni.com/ranzy-ransomware-sample-download.html

![Ransomware Executable](https://statics.bsafes.com/images/publications/flash-2021-1025-indicatiors-of-compormise-associated-with-ranzy-locker-ransomeware-fig-4.png)

![Ransomware Executable](https://statics.bsafes.com/images/publications/flash-2021-1025-indicatiors-of-compormise-associated-with-ranzy-locker-ransomeware-fig-5.png)

In addition to encrypting files and deleting all backups found on the computer, the Ranzy Locker
executable attempts to move laterally to other machines on the same network.

## Additional Resources:
For additional resources related to the prevention and mitigation of ransomware, go to https://www.stopransomware.gov as well as the CISA-Multi-State Information Sharing and Analysis Center (MS-ISAC) Joint Ransomware Guide. Stopransomware.gov is the U.S.  Government’s new, official one-stop location for resources to tackle ransomware more effectively.

## Recommended Mitigations:
- Implement regular backups of all data to be stored as air gapped, password protected
copies offline. Ensure these copies are not accessible for modification or deletion from
any system where the original data resides.
- Implement network segmentation, such that all machines on your network are not
accessible from every other machine.
- Install and regularly update antivirus software on all hosts, and enable real time
detection.
- Install updates/patch operating systems, software, and firmware as soon as
updates/patches are released.
- Review domain controllers, servers, workstations, and active directories for new or
unrecognized user accounts.
- Audit user accounts with administrative privileges and configure access controls with
least privilege in mind. Do not give all users administrative privileges.
- Disable unused remote access/Remote Desktop Protocol (RDP) ports and monitor
remote access/RDP logs for any unusual activity.
- Consider adding an email banner to emails received from outside your organization.
- Disable hyperlinks in received emails.
- Use double authentication when logging into accounts or services.

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
