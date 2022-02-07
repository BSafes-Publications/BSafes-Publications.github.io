---
layout: default
title: . 1/26/2022 - Context and Recommendations to Protect Against Malicious Activity by Iranian Cyber Group Emennet Pasargad  
parent: FBI 
nav_order: 978110599 
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
This is the mobile-friendly web version of the [original article](https://www.ic3.gov/Media/News/2022/220126.pdf).

<img src="https://statics.bsafes.com/images/publications/protect-against-malicious-activity-by-iranian-cyber-group-emennet-pasargad.png" alt="Business Email Compromise Actors Targeting State, Local, Tribal, and Territorial" style="display:block; margin:0 auto">

### 26 January 2022
{: .no_toc }
#### PIN Number
{: .no_toc }
### PIN-20220126-001 
{: .no_toc }  
# Context and Recommendations to Protect Against Malicious Activity by Iranian Cyber Group Emennet Pasargad 
{: .no_toc }

1. TOC
{:toc}

## Threat
Starting in August 2020, Emennet Pasargad actors conducted a multi-faceted campaign to interfere in the 2020 US presidential election. As part of this campaign, the actors obtained confidential U.S. voter information from at least one state election website; sent threatening email messages to intimidate voters; created and disseminated a video containing disinformation pertaining to purported but non-existent voting vulnerabilities; attempted to access, without authorization, several states’ voting-related websites; and successfully gained unauthorized access to a U.S. media company’s computer network. During the 2020 election interference campaign, the actors claimed affiliation with the Proud Boys in the voter intimidation and disinformation aspects of the campaign.

In addition to the 2020 U.S. election-focused operation in which the actors masqueraded as members of the Proud Boys, Emennet previously conducted cyber-enabled information operations, including operations that used a false-flag persona. According to FBI information, in late 2018, the group masqueraded as the "Yemen Cyber Army" and crafted messaging critical of Saudi Arabia. Emennet also demonstrated interest in leveraging bulk SMS services, likely as a means to mass-disseminate propaganda or other messaging. 

FBI information indicates Emennet poses a broader cybersecurity threat outside of information operations.  Since 2018, Emennet has conducted traditional cyber exploitation activity targeting several sectors, including news, shipping, travel (hotels and airlines), oil and petrochemical, financial, and telecommunications, in the United States, Europe, and the Middle East. 
 
## Tactics, Techniques, and Procedures 

The FBI is providing a summary of the group's past TTPs to recipients so they can better understand and defend against the group’s future malicious activity.

Emennet is known to use Virtual Private Network (VPN) services to obfuscate the origin of their activity. The group likely uses VPN services including TorGuard, CyberGhost, NordVPN, and Private Internet Access. 

Over the past three years, Emennet conducted reconnaissance and chose potential victims by performing web searches for leading businesses in various sectors such as “top American news sites.” Emennet would then use these results to scan websites for vulnerable software that could be exploited to establish persistent access. In some instances, the objective may have been to exploit a large number of networks/websites in a particular sector as opposed to a specific organization target. In other situations, Emennet would also attempt to identify hosting/shared hosting services. 

After the initial reconnaissance phase, Emennet typically researched how to exploit specific software, including identifying open source available tools. In particular, Emennet demonstrated interest in identifying webpages running PHP code and identifying externally accessible mysql databases (in particular, phpMyAdmin). Emennet also demonstrated an interest in exploiting the below software applications:

- Wordpress (in particular the revslider and layerslider plugins)
- Drupal
- Apache Tomcat
- Ckeditor and Fckeditor (including the exploitation of Roxy Fileman)

Emennet also expressed interest in numerous specific vulnerabilities, outlined in Appendix A.

When conducting research, Emennet attempted to identify default passwords for particular applications a target may be using, and tried to identify admin and/or login pages associated with those same targeted websites. It should be assumed Emennet may attempt common plaintext passwords for any login sites they identify. 

Emennet is known to use the open source penetration testing tools SQLmap and the commercially available tool Acunetix during operational activity. They also likely use the below tools or resources:

- DefenseCode Web Security Scanner
- Wappalyzer
- Dnsdumpster
- Tiny mce scanner
- Netsparker
- Wordpress security scanner (wpscan)
- Shodan

FBI information indicates the group has attempted to leverage cyber intrusions conducted by other actors for their own benefit. This includes searching for data hacked and leaked by other actors, and attempting to identify webshells that may have been placed or used by other cyber actors. 

***

## Recommendations 
The FBI encourages service providers and other relevant partners to maintain business continuity plans to minimize essential service interruptions. Given the increase in remote work environments and increased use of digitalized infrastructure, to include the use of Virtual Private Network (VPS) services, the FBI encourages regularly monitoring networks and employing best practices. The FBI also suggests reviewing or establishing security policies, user agreements, and patching plans to address current threats posed by malicious cyber actors. 

### Network Best Practices
- Patch and update operating systems, software, and firmware as soon as manufacturer updates are available.
- Regularly change network system and account passwords, and avoid re-using passwords for multiple accounts.
- Utilize multi-factor authentication when possible.
- Monitor remote access/Remote Desktop Protocol (RDP) logs and disable unused remote access/RDP ports.
- Implement listing policies for applications and remote access that only allow systems to execute known and permitted programs under an established security policy.
- Regularly audit administrative user accounts and configure access controls under the concept of least privilege.
- Regularly audit logs to ensure new accounts are legitimate users.
- Scan network for open and listening ports, and mediate those that are unnecessary.
- Identify and create offline backups for critical assets.
- Implement network segmentation.
- Automatically update antivirus and anti-malware solutions and conduct regular virus and malware scans. 

### Remote Work Environment Best Practices
Given the increase in remote work environments and use of Virtual Private Network (VPN) services due to COVID-19, the FBI encourages regularly monitoring these networks and employing best practices. 
- Regularly update VPNs, network infrastructure devices, and devices used for remote work environments with the latest software patches and security configurations.
- When possible, implement multi-factor authentication on all VPN connections. Physical security tokens are the most secure form of multi-factor authentication, followed by authenticator applications. When multi-factor authentication is unavailable, require employees engaging in remote work to use strong passwords.
- Monitor network traffic for unapproved and unexpected protocols.
- Reduce potential attack surface by discontinuing unused VPN servers that may be used as a point of entry for attackers. 

### Ransomware Best Practices
The FBI does not recommend paying ransoms. Payment does not guarantee files will be recovered and may embolden malicious cyber actors to target additional organizations, encourage other criminal actors to engage in the distribution of malware, and/or may fund illicit activities. Regardless of whether the ransom was paid, the FBI urges organizations to report ransomware incidents to a local FBI field office or file a report with the FBI’s Internet Crime Complaint Center (IC3) at IC3.gov. In addition to the above network best practices, the FBI also recommends the following: 
- Maintain offline, encrypted backups of data. Regularly test those backups and keep them current.
- Create, maintain, and exercise a basic cyber incident response plan that includes procedures for
response and notification in a ransomware incident and plans for the possibility of critical systems
being inaccessible for a period of time. 

### User Awareness Best Practices
- Provide end user awareness and training. To help prevent targeted social engineering, ransomware, and phishing scams, ensure that employees and stakeholders are aware of potential cyber threats and how they are delivered. Also provide users with training on information security principles and techniques. 

- Employee knowledge of reporting procedures. Ensure that employees are aware of what to do and who to contact when they see suspicious activity or suspect a cyberattack, to help quickly and efficiently identify threats and employ mitigation strategies. 

***

## Reporting Notice 
The FBI encourages recipients of this document to report information concerning suspicious or criminal activity to their local FBI field office. Field office contacts can be identified at www.fbi.gov/contact-us/fieldoffices. When available, each report submitted should include the date, time, location, type of activity, number of people, and type of equipment used for the activity, the name of the submitting company or organization, and a designated point of contact.

***

## Administrative Note
This product is marked TLP:WHITE. Subject to standard copyright rules, TLP:WHITE information may be distributed without restriction.  

<div style="background-color:lightblue; padding:20px" markdown="1"> 
<h3 style="text-align:center">Your Feedback Regarding this Product is Critical</h3>
Please take a few minutes to send us your feedback. Your feedback
submission may be anonymous. We read each submission carefully, and your
feedback will be extremely valuable to the FBI. Feedback should be specific to
your experience with our written products to enable the FBI to make quick
and continuous improvements to these products. Feedback may be
submitted online here: [https://www.ic3.gov/PIFSurvey](https://www.ic3.gov/PIFSurvey)
</div>
</div>

