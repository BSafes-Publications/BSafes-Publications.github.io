---
layout: default
title: . 2/16/2022 - Russian State-Sponsored Cyber Actors Target Cleared Defense Contractor Networks to Obtain Sensitive U.S. Defense Information and Technology 
parent: FBI 
nav_order: 978101599 
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
This is the mobile-friendly web version of the [original article](https://media.defense.gov/2022/Feb/15/2002939184/-1/-1/0/AA22-047A_Russian_State_Sponsored_Cyber_Actors_Target_CDC_Networks_20220216.PDF).

<img src="https://statics.bsafes.com/images/publications/joint-cyber-security-advisory-2022-02-16-russian-state-sponsored-cyber-actors-target-cleared-defense-contractor-networks.png" alt="Russian State-Sponsored Cyber Actors Target Cleared Defense Contractor Networks to Obtain Sensitive U.S. Defense Information and Technology" style="display:block; margin:0 auto">

### February 16, 2022
{: .no_toc }

# Russian State-Sponsored Cyber Actors Target Cleared Defense Contractor Networks to Obtain Sensitive U.S. Defense Information and Technology  
{: .no_toc }

## Co-Authored by: FBI, NSA, CISA
{: .no_toc }

Product ID:AA22-047A 

1. TOC
{:toc}

TLP WHITE

## Summary
From at least January 2020, through February 2022, the Federal Bureau of Investigation (FBI), National Security Agency (NSA), and Cybersecurity and Infrastructure Security Agency (CISA) have observed regular targeting of U.S. cleared defense contractors (CDCs) by Russian state-sponsored cyber actors. The actors have targeted both large and small CDCs and subcontractors with varying levels of cybersecurity protocols and resources.  These CDCs support contracts for the U.S. Department of Defense (DoD) and Intelligence Community in the following areas: 

- Command, control, communications, and combat systems;
- Intelligence, surveillance, reconnaissance, and targeting;
- Weapons and missile development;
- Vehicle and aircraft design; and
- Software development, data analytics, computers, and logistics. 

Historically, Russian state-sponsored cyber actors have used common but effective tactics to gain access to target networks, including spearphishing, credential harvesting, brute force/password spray techniques, and known vulnerability exploitation against accounts and networks with weak security.  These actors take advantage of simple passwords, unpatched systems, and unsuspecting employees to gain initial access before moving laterally through the network to establish persistence and
exfiltrate data.

![Actions to Help Protect Against Russian State-Sponsored Malicious Cyber Activity:](https://statics.bsafes.com/images/publications/joint-cyber-security-advisory-2022-02-16-russian-state-sponsored-cyber-actors-target-cleared-defense-contractor-networks-cap-1.png)

*This document was developed by the FBI, NSA, and CISA in furtherance of their respective cybersecurity missions, including their responsibilities to develop and issue cybersecurity specifications and mitigations.* 
{: .fs-2}

*This document is marked TLP:WHITE. Disclosure is not limited. Sources may use TLP:WHITE when information carries minimal or no foreseeable risk of misuse, in accordance with applicable rules and procedures for public release. Subject to standard copyright rules, TLP:WHITE information may be distributed without restriction. For more information on the Traffic Light Protocol, see https://www.cisa.gov/tlp.*
{: .fs-2}

In many attempted compromises, these actors have employed similar tactics to gain access to enterprise and cloud networks, prioritizing their efforts against the widely used Microsoft 365 (M365) environment. The actors often maintain persistence by using legitimate credentials and a variety of malware when exfiltrating emails and data.

These continued intrusions have enabled the actors to acquire sensitive, unclassified information, as well as CDC-proprietary and export-controlled technology. The acquired information provides significant insight into U.S. weapons platforms development and deployment timelines, vehicle specifications, and plans for communications infrastructure and information technology. By acquiring proprietary internal documents and email communications, adversaries may be able to adjust their own military plans and priorities, hasten technological development efforts, inform foreign policymakers of U.S. intentions, and target potential sources for recruitment. Given the sensitivity of information widely available on unclassified CDC networks, the FBI, NSA, and CISA anticipate that Russian state-sponsored cyber actors will continue to target CDCs for U.S. defense information in the near future. These agencies encourage all CDCs to apply the recommended mitigations in this advisory, regardless of evidence of compromise

For additional information on Russian state-sponsored cyber activity, see CISA's webpage, Russia
Cyber Threat Overview and Advisories.

## THREAT DETAILS
### Targeted Industries and Assessed Motive
Russian state-sponsored cyber actors have targeted U.S. CDCs from at least January 2020, through February 2022. The actors leverage access to CDC networks to obtain sensitive data about U.S.  defense and intelligence programs and capabilities. Compromised entities have included CDCs supporting the U.S. Army, U.S. Air Force, U.S. Navy, U.S. Space Force, and DoD and Intelligence programs.

During this two-year period, these actors have maintained persistent access to multiple CDC networks, in some cases for at least six months. In instances when the actors have successfully obtained access, the FBI, NSA, and CISA have noted regular and recurring exfiltration of emails and data. For example, during a compromise in 2021, threat actors exfiltrated hundreds of documents related to the company’s products, relationships with other countries, and internal personnel and legal matters.

Through these intrusions, the threat actors have acquired unclassified CDC-proprietary and exportcontrolled information. This theft has granted the actors significant insight into U.S. weapons platforms development and deployment timelines, plans for communications infrastructure, and specific technologies employed by the U.S. government and military. Although many contract awards and descriptions are publicly accessible, program developments and internal company communications remain sensitive. Unclassified emails among employees or with government customers often contain proprietary details about technological and scientific research, in addition to program updates and funding statuses. See figures 1 and 2 for information on targeted customers, industries, and information.

![Figure 1. Targeted Industries](https://statics.bsafes.com/images/publications/joint-cyber-security-advisory-2022-02-16-russian-state-sponsored-cyber-actors-target-cleared-defense-contractor-networks-fig-1.png)
Figure 1. Targeted Industries


![Figure 2. Exfiltrated Information](https://statics.bsafes.com/images/publications/joint-cyber-security-advisory-2022-02-16-russian-state-sponsored-cyber-actors-target-cleared-defense-contractor-networks-fig-2.png)
Figure 2. Exfiltrated Information

### Threat Actor Activity
*Note: This advisory uses the MITRE ATT&CK® for Enterprise framework, version 10. See the ATT&CK for Enterprise for all referenced threat actor tactics and techniques. See the Tactics, Techniques, and Procedures (TTPs) section for a table of the threat actors’ activity mapped to MITRE ATT&CK tactics and techniques.*

#### *Initial Access*
Russian state-sponsored cyber actors use brute force methods, spearphishing, harvested credentials, and known vulnerabilities to gain initial access to CDC networks.

- Threat actors use brute force techniques [T1110] to identify valid account credentials [T1589.001] for domain and M365 accounts. After obtaining domain credentials, the actors use them to gain initial access to the networks. Note: For more information, see joint NSAFBI-CISA Cybersecurity Advisory: Russian GRU Conducting Global Brute Force Campaign to Compromise Enterprise and Cloud Environments.
- Threat actors send spearphishing emails with links to malicious domains [T1566.002] and use publicly available URL shortening services to mask the link [T1027]. Embedding shortened URLs instead of actor-controlled malicious domains is an obfuscation technique meant to bypass virus and spam scanning tools. The technique often promotes a false legitimacy to the email recipient, increasing the probability of a victim’s clicking on the link.
- The threat actors use harvested credentials in conjunction with known vulnerabilities—for example, CVE-2020-0688 and CVE-2020-17144—on public-facing applications [T1078, T1190], such as virtual private networks (VPNs), to escalate privileges and gain remote code execution (RCE) on the exposed applications.<sup>1</sup> In addition, threat actors have exploited CVE2018-13379 on FortiClient to obtain credentials to access networks.
- As CDCs find and patch known vulnerabilities on their networks, the actors alter their tradecraft to seek new means of access. This activity necessitates CDCs maintain constant vigilance for software vulnerabilities and out-of-date security configurations, especially in internet-facing systems.

#### *Credential Access*
After gaining access to networks, the threat actors map the Active Directory (AD) and connect to domain controllers, from which they exfiltrate credentials and export copies of the AD database ntds.dit [T1003.003]. In multiple instances, the threat actors have used Mimikatz to dump admin credentials from the domain controllers.

#### *Collection*
Using compromised M365 credentials, including global admin accounts, the threat actors can gain access to M365 resources, including SharePoint pages [T1213.002], user profiles, and user emails [T1114.002].

#### *Command and Control*
The threat actors routinely use virtual private servers (VPSs) as an encrypted proxy. The actors use VPSs, as well as small office and home office (SOHO) devices, as operational nodes to evade detection [T1090.003]. 

#### *Persistence*
In multiple instances, the threat actors maintained persistent access for at least six months. Although the actors have used a variety of malware to maintain persistence, the FBI, NSA, and CISA have also observed intrusions that did not rely on malware or other persistence mechanisms. In these cases, it is likely the threat actors relied on possession of legitimate credentials for persistence [T1078], enabling them to pivot to other accounts, as needed, to maintain access to the compromised environments. 

### Tactics, Techniques, and Procedures
The following table maps observed Russian state-sponsored cyber activity to the MITRE ATT&CK for Enterprise framework. Several of the techniques listed in the table are based on observed procedures in contextual order. Therefore, some of the tactics and techniques listed in their respective columns appear more than once. See Appendix A for a functional breakdown of TTPs. *Note: For specific
countermeasures related to each ATT&CK technique, see the Enterprise Mitigations section and
MITRE D3FEND™.*


Table 1: Observed Tactics, Techniques, and Procedures (TTPs)
![Table 1: Observed Tactics, Techniques, and Procedures (TTPs)](https://statics.bsafes.com/images/publications/joint-cyber-security-advisory-2022-02-16-russian-state-sponsored-cyber-actors-target-cleared-defense-contractor-networks-table-1-1.png)
![Table 1: Observed Tactics, Techniques, and Procedures (TTPs)](https://statics.bsafes.com/images/publications/joint-cyber-security-advisory-2022-02-16-russian-state-sponsored-cyber-actors-target-cleared-defense-contractor-networks-table-1-2.png)
![Table 1: Observed Tactics, Techniques, and Procedures (TTPs)](https://statics.bsafes.com/images/publications/joint-cyber-security-advisory-2022-02-16-russian-state-sponsored-cyber-actors-target-cleared-defense-contractor-networks-table-1-3.png)
![Table 1: Observed Tactics, Techniques, and Procedures (TTPs)](https://statics.bsafes.com/images/publications/joint-cyber-security-advisory-2022-02-16-russian-state-sponsored-cyber-actors-target-cleared-defense-contractor-networks-table-1-4.png)

## DETECTION
The FBI, NSA, and CISA urge all CDCs to investigate suspicious activity in their enterprise and cloud environments. *Note: For additional approaches on uncovering malicious cyber activity, see joint advisory Technical Approaches to Uncovering and Remediating Malicious Activity, authored by CISA and the cybersecurity authorities of Australia, Canada, New Zealand, and the United Kingdom*

### Detect Unusual Activity
**Implement robust log collection and retention**. Robust logging is critical for detecting unusual activity. Without a centralized log collection and monitoring capability, organizations have limited ability to investigate incidents or detect the threat actor behavior described in this advisory.  Depending on the environment, tools and solutions include: 
• Cloud native solutions, such as cloud-native security incident and event management (SIEM) tools.
• Third-party tools, such as Sparrow, to review Microsoft cloud environments and to detect unusual activity, service principals, and application activity. *Note: For guidance on using these and other detection tools, refer to CISA Cybersecurity Advisory Detecting Post-Compromise Threat Activity in Microsoft Cloud Environments.*

### Look for Evidence of Known TTPs
- Look for behavioral evidence or network and host-based artifacts from known TTPs associated with this activity. To detect password spray activity, review authentication logs for system and application login failures of valid accounts. Look for frequent, failed authentication attempts across multiple accounts.
- To detect use of compromised credentials in combination with a VPS, follow the steps below:
    - **Review logs for suspicious “impossible logins,”** such as logins with changing usernames, user agent strings, and IP address combinations or logins where IP addresses do not align to the expected user’s geographic location. 
    - **Look for one IP used for multiple accounts,** excluding expected logins.
    - **Search for “impossible travel,”** which occurs when a user logs in from multiple IP addresses that are a significant geographic distance apart (i.e., a person could not realistically travel between the geographic locations of the two IP addresses in the time between logins). *Note: This detection opportunity can result in false positives if legitimate users apply VPN solutions before connecting to networks.*
    - **Evaluate processes and program execution command-line arguments** that may indicate credential dumping, especially attempts to access or copy the ntds.dit file from a domain controller.
    - **Identify suspicious privileged account use** after resetting passwords or applying user account mitigations.
    - **Review logs for unusual activity** in typically dormant accounts.
    - **Look for unusual user agent strings,** such as strings not typically associated with normal user activity, which may indicate bot activity.

## INCIDENT RESPONSE AND REMEDIATION 
Organizations with evidence of compromise should assume full identity compromise and initiate a full
identity reset.
- **Reset passwords for all local accounts.** These accounts should include Guest, HelpAssistant, DefaultAccount, System, Administrator, and krbtgt. It is essential to reset the password for the krbtgt account, as this account is responsible for handling Kerberos ticket requests as well as encrypting and signing them. *Note: Reset the krbtgt account twice and consecutively with a 10-hour waiting period between resets (i.e., perform the first krbtgt password reset, wait 10 hours, and then follow with a second krbtgt password reset). The krbtgt password resets may take a long time to propagate fully on large AD environments.  Refer to Microsoft’s AD Forest Recovery - Resetting the krbtgt password guidance and automation script for additional information.  <sup>4,5</sup>*
- **Reset all domain user, admin, and service account passwords.**

*Note: For guidance on evicting advanced persistent threat (APT) actors from cloud and enterprise environments, refer to CISA Analysis Report Eviction Guidance for Networks Affected by the SolarWinds and Active Directory/Microsoft 365 (M365) Compromise. Although this guidance was drafted for federal agencies compromised by the Russian Foreign Intelligence Service (SVR) via the SolarWinds Orion supply chain compromise, the steps provided in the Eviction Phase are applicable for all organizations crafting eviction plans for suspected APT actors.*

## MITIGATIONS
The FBI, NSA, and CISA encourage all CDCs, with or without evidence of compromise, to apply the following mitigations to reduce the risk of compromise by this threat actor. While these mitigations are not intended to be all-encompassing, they address common TTPs observed in these intrusions and will help to mitigate against common malicious activity.  

### Implement Credential Hardening
#### *Enable Multifactor Authentication*
- **Enable multifactor authentication (MFA)** for all users, without exception. Subsequent authentication may not require MFA, enabling the possibility to bypass MFA by reusing single factor authentication assertions (e.g., Kerberos authentication). Reducing the lifetime of assertions will cause account re-validation of their MFA requirements.<sup>6</sup> Service accounts should not use MFA. Automation and platform features (e.g., Group Managed Service Accounts, gMSA) can provide automatic and periodic complex password management for service accounts, reducing the threat surface against single factor authentication assertions.<sup>7</sup> 

#### *Enforce Strong, Unique Passwords*
- **Require accounts to have strong, unique passwords.** Passwords should not be reused across multiple accounts or stored on the system where an adversary may have access.
- **Enable password management functions**, such as Local Administrator Password Solution (LAPS), for local administrative accounts. This will reduce the burden of users’ managing passwords and encourage them to have strong passwords. 

#### *Introduce Account Lockout and Time-Based Access Features*
- **Implement time-out and lock-out features** in response to repeated failed login attempts.
- **Configure time-based access for accounts set at the admin level and higher**  For example, the Just-In-Time (JIT) access method provisions privileged access when needed and can support enforcement of the principle of least privilege (as well as the Zero Trust model). This is a process where a network-wide policy is set in place to automatically disable administrator accounts at the AD level when the account is not in direct need. When the account is needed, individual users submit their requests through an automated process that enables access to a system but only for a set timeframe to support task completion.

#### *Reduce Credential Exposure*
- **Use virtualization solutions on modern hardware and software** to ensure credentials are securely stored, and protect credentials via capabilities, such as Windows Defender Credential Guard (CredGuard) and Trusted Platform Module (TPM).<sup>8</sup> Protecting domain credentials with CredGuard requires configuration and has limitations in protecting other types of credentials (e.g., WDigest and local accounts).<sup>9,10</sup> CredGuard uses TPMs to protect stored credentials. TPMs function as a system integrity observer and trust anchor ensuring the integrity of the boot sequence and mechanisms (e.g., UEFI Secure Boot). Installation of Windows <sup>11</sup> requires TPM v2.0.11 Disabling WDigest and rolling expiring NTLM secrets in smartcards will further protect other credentials not protected by CredGuard.<sup>12,13</sup>

### Establish Centralized Log Management
- **Create a centralized log management system.** Centralized logging applications allow network defenders to look for anomalous activity, such as out-of-place communications between devices or unaccountable login failures, in the network environment. 
    - Forward all logs to a SIEM tool.
    - Ensure logs are searchable.
    - Retain critical and historic network activity logs for a minimum of 180 days. 
- **If using M365, enable Unified Audit Log (UAL)**—M365’s logging capability—which contains events from Exchange Online, SharePoint online, OneDrive, Azure AD, Microsoft Teams, PowerBI, and other M365 services.
- **Correlate logs, including M365 logs, from network and host security devices** This correlation will help with detecting anomalous activity in the network environment and connecting it with potential anomalous activity in M365. 

In addition to setting up centralized logging, organizations should:
- **Ensure PowerShell logging is turned on.** Threat actors often use PowerShell to hide their malicious activities.<sup>14</sup>
- **Update PowerShell instances to version 5.0 or later** and uninstall all earlier versions of PowerShell. Logs from prior versions are either non-existent or do not record enough detail to aid in enterprise monitoring and incident response activities. 
- **Confirm PowerShell 5.0 instances have module, script block, and transcription logging** enabled.
- **Monitor remote access/Remote Desktop Protocol (RDP) logs** and disable unused remote access/RDP ports.

### Initiate a Software and Patch Management Program 
- **Consider using a centralized patch management system.** Failure to deploy software patches in a timely manner makes an organization a target of opportunity, increasing its risk of compromise. Organizations can ensure timely patching of software vulnerabilities by implementing an enterprise-wide software and patch management program.<sup>15</sup>
    - If an organization is unable to update all software shortly after a patch is released, **prioritize patches for CVEs that are already known** to be exploited or that would be accessible to the largest number of potential adversaries (such as internet-facing systems).
    - **Subscribe to CISA cybersecurity notifications and advisories** to keep up with known exploited vulnerabilities, security updates, and threats. This will assist organizations in maintaining situational awareness of critical software vulnerabilities and, if applicable, associated exploitation.- **Sign up for CISA’s** cyber hygiene services, including vulnerability scanning, to help reduce
exposure to threats. CISA’s vulnerability scanning service evaluates external network presence by executing continuous scans of public, static IPs for accessible services and vulnerabilities. 

### Employ Antivirus Programs 
- **Ensure that antivirus applications are installed on all organizations’ computers** and are configured to prevent spyware, adware, and malware as part of the operating system security baseline.
- **Keep virus definitions up to date.**
- **Regularly monitor antivirus scans.**

### Use Endpoint Detection and Response Tools 
- **Utilize endpoint detection and response (EDR) tools.** These tools allow a high degree of visibility into the security status of endpoints and can be an effective defense against threat actors. EDR tools are particularly useful for detecting lateral movement, as they have insight into common and uncommon network connections for each host. 

### Maintain Rigorous Configuration Management Programs
- **Audit configuration management programs** to ensure they can track and mitigate emerging threats. Review system configurations for misconfigurations and security weaknesses. Having a robust configuration program hinders sophisticated threat operations by limiting the effectiveness of opportunistic attacks.<sup>16</sup>

### Enforce the Principle of Least Privilege
- **Apply the principle of least privilege.** Administrator accounts should have the minimum permissions they need to do their tasks. This can reduce the impact if an administrator account is compromised.  
- **For M365, assign administrator roles to role-based access control (RBAC)** to implement the principle of least privilege. Given its high level of default privilege, you should only use the Global Administrator account when absolutely necessary. Using Azure AD’s numerous other built-in administrator roles instead of the Global Administrator account can limit assigning unnecessary privileges. *Note: Refer to the Microsoft documentation, Azure AD built-in roles,
for more information about Azure AD.*
- **Remove privileges not expressly required by an account’s function or role**
- **Ensure there are unique and distinct administrative accounts** for each set of administrative tasks.
- **Create non-privileged accounts for privileged users,** and ensure they use the nonprivileged accounts for all non-privileged access (e.g., web browsing, email access).
- **Reduce the number of domain and enterprise administrator accounts,** and remove all accounts that are unnecessary.
- **Regularly audit administrative user accounts.**
- **Regularly audit logs to ensure new accounts are legitimate users.**
- **Institute a group policy that disables remote interactive logins,** and use Domain Protected Users Group.

To assist with identifying suspicious behavior with administrative accounts:
- **Enable alerts on privilege escalations and role changes.**
- **Log privileged user changes**  in the network environment, and create an alert for unusual events.

### Review Trust Relationships
- **Review existing trust relationships with IT service providers,**  such as managed service providers (MSPs) and cloud service providers (CSPs). Threat actors are known to exploit trust relationships between providers and their customers to gain access to customer networks and data. 
- **Remove unnecessary trust relationships.**
_ **Review contractual relationships** with all service providers, and ensure contracts include:
    - Security controls the customer deems appropriate. 
    - Appropriate monitoring and logging of provider-managed customer systems.
    - Appropriate monitoring of the service provider’s presence, activities, and connections to the customer network.
    - Notification of confirmed or suspected security events and incidents occurring on the provider’s infrastructure and administrative networks.

*Note: Review CISA’s page on APTs Targeting IT Service Provider Customers and CISA Insights: Mitigations and Hardening Guidance for MSPs and Small and Mid-sized Businesses for additional recommendations for MSP and CSP customers.*

### Encourage Remote Work Environment Best Practices
With the increase in remote work and use of VPN services due to COVID-19, the FBI, NSA, and CISA encourage regularly monitoring remote network traffic, along with employing the following best practices.*Note: For additional information, see joint NSA-CISA Cybersecurity Information Sheet:
Selecting and Hardening Remote Access VPN Solutions*
- **Regularly update VPNs, network infrastructure devices, and devices used for remote work environments** with the latest software patches and security configurations
- **When possible, require MFA on all VPN connections.**  Physical security tokens are the most secure form of MFA, followed by authenticator applications. When MFA is unavailable, mandate that employees engaging in remote work use strong passwords.
- **Monitor network traffic for unapproved and unexpected protocols.**
- **Reduce potential attack surfaces by discontinuing unused VPN servers** that may be used as a point of entry by adversaries.

### Establish User Awareness Best Practices
Cyber actors frequently use unsophisticated methods to gain initial access, which can often be mitigated by stronger employee awareness of indicators of malicious activity. The FBI, NSA, and CISA recommend the following best practices to improve employee operational security when conducting business:
- **Provide end user awareness and training.** To help prevent targeted social engineering and spearphishing scams, ensure that employees and stakeholders are aware of potential cyber threats and how they are delivered. Also, provide users with training on information security principles and techniques. 
- **Inform employees of the risks of social engineering attacks,** e.g., risks associated with posting detailed career information to social or professional networking sites.
- **Ensure that employees are aware of what to do and whom to contact when they see suspicious activity or suspect a cyber intrusion** to help quickly and efficiently identify threats and employ mitigation strategies. 

### Apply Additional Best Practice Mitigations
- **Deny atypical inbound activity from known anonymization services** including commercial VPN services and The Onion Router (TOR).
- **Impose listing policies for applications and remote access** that only allow systems to execute known and permitted programs under an established security policy.
- **Identify and create offline backups for critical assets.**
- **Implement network segmentation.**
- **Review CISA Alert** AA20-120A: Microsoft Office 365 Security Recommendations for additional recommendations on hardening M365 cloud environments.

## REWARDS FOR JUSTICE PROGRAM
If you have information on state-sponsored Russian cyber operations targeting U.S. critical infrastructure, contact the Department of State’s Rewards for Justice Program. You may be eligible for a reward of up to $10 million, which the Department is offering for information leading to the identification or location of any person who, while acting under the direction or control of a foreign government, participates in malicious cyber activity against U.S. critical infrastructure in violation of the Computer Fraud and Abuse Act (CFAA). Contact (202) 702-7843 on WhatsApp, Signal, or Telegram, or send information via the Rewards for Justice secure Tor-based tips line located on the Dark Web. For more details, refer to rewardsforjustice.net.

## CAVEATS
The information you have accessed or received is being provided “as is” for informational purposes only. The FBI, NSA, and CISA do not endorse any commercial product or service, including any subjects of analysis. Any reference to specific commercial products, processes, or services by service mark, trademark, manufacturer, or otherwise, does not constitute or imply their endorsement, recommendation, or favoring by the FBI, NSA, or CISA.

## CONTACT
To report suspicious activity related to information found in this Joint Cybersecurity Advisory, contact your local FBI field office at www.fbi.gov/contact-us/field-offices or the FBI’s 24/7 Cyber Watch (CyWatch) at (855) 292-3937 or by email at CyWatch@fbi.gov. When available, please include the following information regarding the incident: date, time, and location of the incident; type of activity; number of people affected; type of equipment used for the activity; the name of the submitting company or organization; and a designated point of contact. To request incident response resources or technical assistance related to these threats, contact CISA at Central@cisa.gov. For NSA client requirements or general cybersecurity inquiries, contact the NSA Cybersecurity Requirements Center at (410) 854-4200 or Cybersecurity_Requests@nsa.gov. Defense Industrial Base companies may additionally sign up for NSA’s free cybersecurity services, including Protective DNS, vulnerability scanning, and threat intelligence collaboration at dib_defense@cyber.nsa.gov.

## Appendix: Detailed Tactics, Techniques, and Procedures
### Reconnaissance [TA0043]
Reconnaissance consists of techniques that involve adversaries actively or passively gathering
information that can be used to support targeting. The adversary is known for harvesting login
credentials [T1589.001].<sup>17</sup>
![Reconnaissance](https://statics.bsafes.com/images/publications/joint-cyber-security-advisory-2022-02-16-russian-state-sponsored-cyber-actors-target-cleared-defense-contractor-networks-cap-2.png)

### Initial Access [TA0001]
Initial Access consists of techniques that use various entry vectors to gain their initial foothold within a network. For example, the adversary may obtain and abuse credentials of existing accounts as a means of gaining Initial Access, Persistence, Privilege Escalation, or Defense Evasion [T1078].  <sup>18</sup> These specific actors obtained and abused credentials of domain [T1078.002] and cloud accounts [T1078.004].  <sup>19</sup> The actors also used external remote services to gain access to systems [T1133].<sup>20</sup> The adversary took advantage of weaknesses in internet-facing servers and conducted SQL injection attacks against organizations' external websites [T1190].<sup>21</sup> Finally, they sent spearphishing emails with a malicious link in an attempt to gain access [T1566.002].<sup>22</sup>
![Initial Access](https://statics.bsafes.com/images/publications/joint-cyber-security-advisory-2022-02-16-russian-state-sponsored-cyber-actors-target-cleared-defense-contractor-networks-cap-3.png)

### Persistence [TA0003]
Persistence consists of techniques that adversaries use to keep access to systems across restarts, changed credentials, and other interruptions that could cut off their access. The adversary obtains and abuses credentials of existing accounts as a means of gaining Initial Access, Persistence, Privilege Escalation, or Defense Evasion [T1078]. <sup>23</sup>
![Persistence](https://statics.bsafes.com/images/publications/joint-cyber-security-advisory-2022-02-16-russian-state-sponsored-cyber-actors-target-cleared-defense-contractor-networks-cap-4.png)

### Privilege Escalation [TA0004]
Privilege Escalation consists of techniques that adversaries use to gain higher-level permissions on a system or network. The adversary obtains and abuses credentials of existing accounts as a means of gaining Initial Access, Persistence, Privilege Escalation, or Defense Evasion [T1078].  <sup>24</sup> Specifically in this case, credentials of cloud accounts [T1078.004] were obtained and abused.<sup>25</sup>
![Privilege Escalation](https://statics.bsafes.com/images/publications/joint-cyber-security-advisory-2022-02-16-russian-state-sponsored-cyber-actors-target-cleared-defense-contractor-networks-cap-5.png)

### Defense Evasion [TA0005]
Defense Evasion consists of techniques that adversaries use to avoid detection throughout their compromise. The adversary made its executables and files difficult to discover or analyze by encrypting, encoding, or otherwise obfuscating its contents on the system or in transit [T1027].<sup>26</sup>
![Defense Evasion](https://statics.bsafes.com/images/publications/joint-cyber-security-advisory-2022-02-16-russian-state-sponsored-cyber-actors-target-cleared-defense-contractor-networks-cap-6.png)

### Credential Access [TA0006]
![Credential Access](https://statics.bsafes.com/images/publications/joint-cyber-security-advisory-2022-02-16-russian-state-sponsored-cyber-actors-target-cleared-defense-contractor-networks-cap-7.png)
Credential Access consists of techniques for stealing credentials like account names and passwords.  The adversary attempted to access or create a copy of the Active Directory (AD) domain database to steal credential information, as well as obtain other information about domain members such as devices, users, and access rights [T1003.003].  <sup>27</sup> The adversary also used a single or small list of commonly used passwords against many different accounts to attempt to acquire valid account credentials [T1110.003].<sup>28</sup> 
![Credential Access](https://statics.bsafes.com/images/publications/joint-cyber-security-advisory-2022-02-16-russian-state-sponsored-cyber-actors-target-cleared-defense-contractor-networks-cap-7.png)

### Discovery [TA0007]
Discovery consists of techniques an adversary may use to gain knowledge about the system and internal network. The adversary enumerated files and directories or searched in specific locations of a host or network share for certain information within a file system [T1083].<sup>29</sup> In addition, the adversary attempted to gather information on domain trust relationships that may be used to identify lateral movement opportunities in Windows multi-domain or forest environments [T1482].  <sup>30</sup>
![Discovery](https://statics.bsafes.com/images/publications/joint-cyber-security-advisory-2022-02-16-russian-state-sponsored-cyber-actors-target-cleared-defense-contractor-networks-cap-8.png)

### Collection [TA0009]
Collection consists of both the techniques adversaries may use to gather information and the sources from which information is collected that are relevant to the adversary's objectives. The adversary leverages information repositories, such as SharePoint, to mine valuable information [T1213.002].<sup>31</sup>
![Collection](https://statics.bsafes.com/images/publications/joint-cyber-security-advisory-2022-02-16-russian-state-sponsored-cyber-actors-target-cleared-defense-contractor-networks-cap-9.png)


### Command and Control [TA0011]
Command and Control (C2) consists of techniques that adversaries may use to communicate with systems under their control within a victim network. The adversary chained together multiple proxies to disguise the source of malicious traffic. In this case, TOR and VPN servers are used as multi-hop proxies to route C2 traffic and obfuscate their activities [T1090.003]. <sup>32</sup>
![Command and Control](https://statics.bsafes.com/images/publications/joint-cyber-security-advisory-2022-02-16-russian-state-sponsored-cyber-actors-target-cleared-defense-contractor-networks-cap-10.png)

## ADDITIONAL RESOURCES
***  

<sup>1</sup> NSA, CISA, FBI, NCSC | Cybersecurity Advisory | Russian GRU Conducting Global Brute Force Campaign to Compromise Enterprise and Cloud Environments | 1 July 2021.  
<sup>2</sup> NSA | Cybersecurity Advisory | Mitigating Recent VPN Vulnerabilities | 7 October 2019.  
<sup>3</sup> NSA, CISA, FBI, NCSC | Cybersecurity Advisory | Russian GRU Conducting Global Brute Force Campaign to Compromise Enterprise and Cloud Environments | 1 July 2021.  
<sup>4</sup> Microsoft | Article | AD Forest Recovery – Resetting the krbtgt password | 29 July 2021.  
<sup>5</sup> Microsoft | GitHub | New-KrbtgtKeys.ps1 | 14 May 2020.  
<sup>6</sup> NSA | Cybersecurity Information | Defend Privileges and Accounts | August 2019.  
<sup>7</sup> Microsoft | Article | Group Managed Service Accounts Overview | 29 July 2021.  
<sup>8</sup> NSA | Cybersecurity Information | Leverage Modern Hardware Security Features | August 2019.  
<sup>9</sup> Microsoft | Article | Protect derived domain credentials with Windows Defender Credential Guard | 3 December 2021.  
<sup>10</sup> Microsoft | Article | Windows Defender Credential Guard protection limits | 3 December 2021.  
<sup>11</sup> Microsoft | Article | Windows 11 requirements | 30 November 2021.  
<sup>12</sup> Microsoft | Blog Post | The Importance of KB2871997 and KB2928120 for Credential Protection | 20 September 2021.  
<sup>13</sup> Microsoft | Article | What’s New in Credential Protection | 7 January 2022.  
<sup>14</sup> NSA | Cybersecurity Factsheet | PowerShell: Security Risks and Defenses | 1 December 2016.  
<sup>15</sup> NSA | Cybersecurity Information | Update and Upgrade Software Immediately | August 2019.  
<sup>16</sup> NSA | Cybersecurity Information | Actively Manage Systems and Configurations | August 2019.  
<sup>17</sup> MITRE | Groups | APT28 | 18 October 2021.  
<sup>18</sup> MITRE | Groups | APT28 | 18 October 2021.  
<sup>19</sup> MITRE | Software | Cobalt Strike | 18 October 2021.  
<sup>20</sup> Based on technical information shared by Mandiant.  
<sup>21</sup> MITRE | Groups | APT28 | 18 October 2021.  
<sup>22</sup> Based on technical information shared by Mandiant.  
<sup>23</sup> MITRE | Groups | APT28 | 18 October 2021.  
<sup>24</sup> MITRE | Groups | APT28 | 18 October 2021.  
<sup>25</sup> MITRE | Software | Cobalt Strike | 18 October 2021.  
<sup>26</sup> MITRE | Software | Fysbis | 6 November 2020.  
<sup>27</sup> MITRE | Software | Koadic | 30 March 2020.  
<sup>28</sup> MITRE | Groups | APT28 | 18 October 2021.  
<sup>29</sup> Based on technical information shared by Mandiant.  
<sup>30</sup> Based on technical information shared by Mandiant.  
<sup>31</sup> MITRE | Groups | APT28 | 18 October 2021.  
<sup>32</sup> MITRE | Groups | APT28 | 18 October 2021. 


</div>
