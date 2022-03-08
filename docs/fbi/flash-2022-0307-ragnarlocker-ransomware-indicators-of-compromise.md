---
layout: default
title: . 3/7/2022 - RagnarLocker Ransomware Indicators of Compromise 
parent: FBI 
nav_order: 978092499 
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
This is the mobile-friendly web version of the [original article](https://www.documentcloud.org/documents/21397387-ragnarlocker-ransomware-indicators-of-compromise).

<img src="https://statics.bsafes.com/images/publications/flash-2022-0307-ragnarlocker-ransomware-indicators-of-compromise.png" style="display:block; margin:0 auto">

### 7 March 2022
{: .no_toc }
#### Flash Number
{: .no_toc }
### CU-000163-MW 
{: .no_toc }  

1. TOC
{:toc}

The following information is being provided by the FBI, with no guarantees or warranties, for potential use at the sole discretion of recipients in order to protect against cyber threats. This data is provided to help cyber security professionals and system administrators’ guard against the persistent malicious actions of cyber actors. This FLASH was coordinated with DHS-CISA.

This FLASH has been released TLP WHITE. Subject to standard copyright rules, TLP WHITE information may be distributed without restriction.

**WE NEED YOUR HELP!** If you identify any suspicious activity within your enterprise or have related information, please contact your local FBI Cyber Squad immediately with respect to the procedures outlined in the Reporting Notice section of this message.

***

# RagnarLocker Ransomware Indicators of Compromise    

## Summary
The FBI first became aware of RagnarLocker in April 2020 and subsequently produced a FLASH to disseminate known indicators of compromise (IOCs) at that time. This FLASH provides updated and additional IOCs to supplement that report. As of January 2022, the FBI has identified at least 52 entities across 10 critical infrastructure sectors affected by RagnarLocker ransomware, including entities in the critical manufacturing, energy, financial services, government, and information technology sectors. RagnarLocker ransomware actors work as part of a ransomware family1, frequently changing obfuscation techniques to avoid detection and prevention.

## Technical Details
RagnarLocker is identified by the extension “.RGNR_<ID>,” where <ID> is a hash of the computer’s NETBIOS name. The actors, identifying themselves as “RAGNAR_LOCKER,” leave a .txt ransom note, with instructions on how to pay the ransom and decrypt the data. RagnarLocker uses VMProtect, UPX, and custom packing algorithms and deploys within an attacker’s custom Windows XP virtual machine on a target’s site.

Ragnar Locker uses Windows API GetLocaleInfoW to identify the location of the infected machine. If the victim location is identified as "Azerbaijani," "Armenian," "Belorussian," "Kazakh," "Kyrgyz," "Moldavian," "Tajik," "Russian," "Turkmen," "Uzbek," "Ukrainian," or "Georgian," the process terminates.

RagnarLocker checks for current infections to prevent multiple transform encryption of the data, potentially corrupting it. The binary gathers the unique machine GUID, operating system product name, and user name currently running the process. This data is sent through a custom hashing algorithm to generate a unique identifier: <HashedMachineGuid>-<HashedWindowsProductName>-<HashedUser>-<HashedComputerName>-<HashedAllDataTogether>.

RagnarLocker identifies all attached hard drives using Windows APIs: CreateFileW, DeviceIoControl, GetLogicalDrives, and SetVolumeMountPointA. The ransomware assigns a drive letter to any volumes not assigned a logical drive letter and makes them accessible. These newly attached volumes are later encrypted during the final stage of the binary.

RagnarLocker iterates through all running services and terminates services commonly used by managed service providers to remotely administer networks. The malware then attempts to silently delete all Volume Shadow Copies, preventing user recovery of encrypted files, using two different methods:

- $ vssadmin delete shadows /all /quiet
- $ wmic.exe.shadowcopy.delete

Lastly, RagnarLocker encrypts all available files of interest. Instead of choosing which files to encrypt, RagnarLocker chooses which folders it will not encrypt. Taking this approach allows the computer to continue to operate “normally” while the malware encrypts files with known and unknown extensions containing data of value to the victim. For example, if the logical drive being processed is the C: drive, the malware does not encrypt files in the following folders:

- Windows
- Windows.old 
- Mozilla 
- Mozilla Firefox 
- Tor browser 
- Internet Explorer 
- $Recycle.Bin 
- Program Data 
- Google 
- Opera 
- Opera Software

Also, when iterating through files, the malware does not encrypt files with the following extensions:

- .db 
- .sys 
- .dll 
- .lnk 
- .msi 
- .drv 
- .exe

## Indicators
The following IOCs are associated with RagnarLocker ransomware, as of January 2022.

![](https://statics.bsafes.com/images/publications/flash-2022-0307-ragnarlocker-ransomware-indicators-of-compromise-cap-1.png)
![](https://statics.bsafes.com/images/publications/flash-2022-0307-ragnarlocker-ransomware-indicators-of-compromise-cap-2.png)
![](https://statics.bsafes.com/images/publications/flash-2022-0307-ragnarlocker-ransomware-indicators-of-compromise-cap-3.png)
![](https://statics.bsafes.com/images/publications/flash-2022-0307-ragnarlocker-ransomware-indicators-of-compromise-cap-4.png)
![](https://statics.bsafes.com/images/publications/flash-2022-0307-ragnarlocker-ransomware-indicators-of-compromise-cap-5.png)

## Information Requested:
The FBI does not encourage paying a ransom to criminal actors. Paying a ransom may embolden adversaries to target additional organizations, encourage other criminal actors to engage in the distribution of ransomware, or fund illicit activities. Paying the ransom also does not guarantee a victim’s files will be recovered. However, the FBI understands when businesses are faced with an inability to function, executives will evaluate all options to protect their shareholders, employees, and customers. Regardless of whether you or your organization decides to pay the ransom, the FBI urges you to report ransomware incidents to your local field office. Doing so provides investigators and analysts with the critical information they need to track ransomware attackers, hold them accountable under US law, and prevent future attacks.

The FBI may seek the following information:

### SHORT TERM ITEMS

- Copy of the ransom note (screen shot/picture/text file).
- Any discovered malicious IPs with time stamps/time zones (unusual RDP connections/unusual VPN connections/beacons to malicious IPs).
- Virtual currency addresses/amount of demand.
- Any malicious files (executables/binaries).
- Summary of timeline of events (dates of initial observation/malicious activity).
- Evidence of data exfiltration.

### LONG TERM ITEMS

- Brief summary of where the IOCs came from.
- Incident response report.
- Copy of any communications with malicious actors.
- Forensic images and memory captures.
- Host and network logs.
- Any available decryptor.
- Scope of impact (amount of loss).

## Recommended Mitigations:

- Back-up critical data offline.
- Ensure copies of critical data are in the cloud or on an external hard drive or storage device. This information should not be accessible from the compromised network.
- Secure your back-ups and ensure data is not accessible for modification or deletion from the system where the data resides.
- Use multi-factor authentication with strong passwords, including for remote access services.
- Keep computers, devices, and applications patched and up-to-date.
- Monitor cyber threat reporting regarding the publication of compromised VPN login credentials and change passwords and settings.
- Consider adding an email banner to emails received from outside your organization.
- Disable unused remote access/Remote Desktop Protocol (RDP) ports and monitor remote access/RDP logs.
- Audit user accounts with administrative privileges and configure access controls with least privilege in mind.
- Implement network segmentation.

## Additional Resources
For additional resources related to the prevention and mitigation of ransomware, go to https://www.stopransomware.gov as well as the CISA-Multi-State Information Sharing and Analysis Center (MS-ISAC) Joint Ransomware Guide. Stopransomware.gov is the Government’s official one-stop location for resources to tackle ransomware more effectively.

CISA’s Ransomware Readiness Assessment (RRA) is a no-cost self-assessment based on a tiered set of practices to help organizations better assess how well they are equipped to defend and recover from a ransomware incident.

CISA offers a range of no-cost cyber hygiene services to help critical infrastructure organizations assess, identify, and reduce their exposure to threats, including ransomware. By requesting these services, organizations of any size could find ways to reduce their risk and mitigate attack vectors.

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
