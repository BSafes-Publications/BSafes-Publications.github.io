---
layout: default
title: . 8/23/2021 - Indicators of Compromise Associated with OnePercent Group Ransomware 
parent: FBI 
nav_order: 979040899 
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
This is the mobile-friendly web version of the [original article](https://s3.documentcloud.org/documents/21047946/onepercent-group-ransomware-bc-flash-alert.pdf).

<img src="https://statics.bsafes.com/images/publications/onepercent-group-ransomware-bc-flash-alert.png" alt="Indicators of Compromise Associated with OnePercent Group Ransomware" style="display:block; margin:0 auto">

### 23 Aug 2021
{: .no_toc }
#### Alert Number
{: .no_toc }
### CU-000149-MW 
{: .no_toc }  

1. TOC
{:toc}

The following information is being provided by the FBI, with no guarantees or warranties, for potential use at the sole discretion of recipients in order to protect against cyber threats. This data is provided to help cyber security professionals and system administrators’ guard against the persistent malicious actions of cyber actors. This FLASH was coordinated with DHS-CISA.

This FLASH has been released TLP WHITE. Subject to standard copyright rules, TLP WHITE information may be distributed without restriction.

# Indicators of Compromise Associated with OnePercent Group Ransomware 

## Summary
The FBI has learned of a cyber-criminal group who self identifies as the “OnePercent Group” and who have used Cobalt Strike to perpetuate ransomware attacks against US companies since November 2020. OnePercent Group actors compromise victims through a phishing email in which an attachment is opened by the user. The attachment’s macros infect the system with the IcedID1 banking trojan. IcedID downloads additional software to include Cobalt Strike. Cobalt Strike moves laterally in the network, primarily with PowerShell remoting.

OnePercent Group actors encrypt the data and exfiltrate it from the victims’ systems. The actors contact the victims via telephone and email, threatening to release the stolen data through The Onion Router (TOR) network and clearnet, unless a ransom is paid in virtual currency. OnePercent Group actors’ extortion tactics always begin with a warning and progress from a partial leak of data to a full leak of all the victim’s exfiltrated data. The extortion/data leak typically follows these steps:

- *Leak Warning:* After initially gaining access to a victim network, OnePercent Group actors leave a ransom note stating the data has been encrypted and exfiltrated. The note states the victim needs to contact the OnePercent Group actors on TOR or the victim data will be leaked. If the victim does not make prompt communication within a week of infection, the OnePercent Group actors follow up with emails and phone calls to the victim stating the data will be leaked.

- *One Percent Leak:* If the victim does not pay the ransom quickly, the OnePercent Group actors threaten to release a portion of the stolen data to various clearnet websites.

- *Full Leak:* f the ransom is not paid in full after the “one percent leak”, OnePercent Group actors threaten to sell the stolen data to the Sodinokibi Group2 to publish at an auction.

## Ransom Note Details and TOR Website 
OnePercent Group ransom notes are uniquely named and provide a link to the TOR website, which victims must access by downloading and using a TOR browser. This website is used to communicate the ransom amount, provide technical support, and negotiate with the victims via an online chat functionality. The victims are instructed to pay the ransom to a Bitcoin address, and advised that a decryption key will be provided in 24-48 hours after payment.

![24-48 hours after payment](https://statics.bsafes.com/images/publications/flash-2021-0823-indicators-of-compromise-associated-with-onepercent-group-ransomware-fig-1.png)

## File Names and Tools used by Attackers 
The following applications are leveraged by OnePercent actors to compromise victims. While some of these applications support legitimate purposes, they can also be used by threat actors to aid in system compromise or exploration of a victim company’s enterprise network:

- AWS S3 cloud
- IcedID
- Cobalt Strike
- Powershell
- Rclone
- Mimikatz
- SharpKatz
- BetterSafetyKatz
- SharpSploit

## Technical Details 
OnePercent Group actors gain unauthorized access to victim networks through phishing emails with a malicious zip file attachment. The zip file includes a Microsoft Word or Excel document that contains malicious macros that allow the actors to subsequently infect the victim’s system with the banking Trojan IcedID. The actors use IcedID to install and execute the software Cobalt Strike on the victim’s network to move laterally to other systems within the environment through PowerShell remoting. The actors use rclone for data exfiltration from the victim’s network. The actors have been observed within the victim’s network for approximately one month prior to deployment of the ransomware.

Once the ransomware is successfully deployed, the victim will start to receive phone calls through spoofed phone numbers with ransom demands and are provided a ProtonMail email address for further communication. The actors will persistently demand to speak with a victim company’s designated negotiator or otherwise threaten to publish the stolen data. When a victim company does not respond, the actors send subsequent threats to publish the victim company’s stolen data via the same ProtonMail email address.

The FBI identified the following indicators of compromise (IOCs) that we assess are likely associated with this activity.

![associated with this activity.](https://statics.bsafes.com/images/publications/flash-2021-0823-indicators-of-compromise-associated-with-onepercent-group-ransomware-fig-2.png)
![associated with this activity.](https://statics.bsafes.com/images/publications/flash-2021-0823-indicators-of-compromise-associated-with-onepercent-group-ransomware-fig-3.png)

![associated with this activity.](https://statics.bsafes.com/images/publications/flash-2021-0823-indicators-of-compromise-associated-with-onepercent-group-ransomware-fig-4.png)

![associated with this activity.](https://statics.bsafes.com/images/publications/flash-2021-0823-indicators-of-compromise-associated-with-onepercent-group-ransomware-fig-5.png)

## Recommended Mitigations 
Due to the attackers in question utilizing the rclone program, it is recommended that affected organizations be aware of the following hashes associated with rclone:

![hashes associated with rclone](https://statics.bsafes.com/images/publications/flash-2021-0823-indicators-of-compromise-associated-with-onepercent-group-ransomware-fig-6.png)

- Back-up critical data offline.
- Ensure administrators are not using “Admin Approval” mode.
- Implement Microsoft LAPS, if possible.
- Ensure copies of critical data are in the cloud or on an external hard drive or storage device. This
information should not be accessible from the compromised network.
- Secure your back-ups and ensure data is not accessible for modification or deletion from the
system where the original data resides.
- Keep computers, devices, and applications patched and up-to-date.
- Consider adding an email banner to emails received from outside your organization.
- Disable unused remote access/Remote Desktop Protocol (RDP) ports and monitor remote
access/RDP logs.
- Audit user accounts with administrative privileges and configure access controls with least privilege
in mind.
- Implement network segmentation.
- Use multi-factor authentication with strong passphrases.


## Additional Resources
For additional resources related to the prevention and mitigation of ransomware, go to https://www.stopransomware.gov as well as the CISA-Multi-State Information Sharing and Analysis Center (MS-ISAC) Joint Ransomware Guide. Stopransomeware.gov is the U.S. Government’s new, official one-stop location for resources to tackle ransomware more effectively.

## Reporting Notice
The FBI does not encourage paying ransoms. Payment does not guarantee files will be recovered. It may also embolden adversaries to target additional organizations, encourage other criminal actors to engage in the distribution of ransomware, and/or fund illicit activities. However, the FBI understands that when victims are faced with an inability to function, all options are evaluated to protect shareholders, employees and customers. Regardless of whether your organization decided to pay the ransom, the FBI urges you to report ransomware incidents to the FBI’s Internet Crime Complaint Center (IC3) (https://ic3.gov). Doing so provides the FBI with critical information needed to prevent future attacks by identifying and tracking ransomware attackers and holding them accountable under U.S. law.

## Administrative Note
This product is marked TLP:WHITE. Subject to standard copyright rules, TLP:WHITE information may be distributed without restriction.

For comments or questions related to the content or dissemination of this product, contact CyWatch.

<div style="background-color:lightblue; padding:20px" markdown="1">
<h3 style="text-align:center">Your Feedback on the Value of this Product Is Critical</h3>
Was this product of value to your organization? Was the content clear and concise? Your comments are very important to us and can be submitted anonymously. Please take a moment to complete the survey at the link below. Feedback should be specific to your experience with our written products to enable the FBI to make quick and continuous improvements to such products. Feedback may be submitted online here: https://www.ic3.gov/PIFSurvey

Please note that this survey is for feedback on content and value only. Reporting of technical information regarding FLASH reports must be submitted through FBI CYWATCH.
</div>
</div>
