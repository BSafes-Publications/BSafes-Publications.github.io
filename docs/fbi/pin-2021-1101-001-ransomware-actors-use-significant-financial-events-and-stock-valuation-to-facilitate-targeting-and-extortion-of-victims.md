---
layout: default
title: . 11/1/2021 - Ransomware Actors Use Significant Financial Events and Stock Valuation to Facilitate Targeting and Extortion of Victims  
parent: FBI 
nav_order: 979013099 
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
This is the mob30e-friendly web version of the [original article](https://www.ic3.gov/Media/News/2021/211101.pdf).

<img src="https://statics.bsafes.com/images/publications/pin-2021-1101-001-ransomware-actors-use-significant-financial-events-and-stock-valuation-to-facilitate-targeting-and-extortion-of-victims.png" alt="Business Email Compromise Actors Targeting State, Local, Tribal, and Territorial" style="display:block; margin:0 auto">

### 01 November 2021
{: .no_toc }
#### PIN Number
{: .no_toc }
### 20211101-001 
{: .no_toc }  
# Ransomware Actors Use Significant Financial Events and Stock Valuation to Facilitate Targeting and Extortion of Victims 
{: .no_toc }

1. TOC
{:toc}

The following information is being provided by the FBI, with no guarantees or warranties, for potential use at the sole discretion of recipients to protect against cyber threats. This data is provided to help cyber security professionals and system administrators guard against the persistent malicious actions of cyber actors. This PIN was coordinated with DHS-CISA.  

This PIN has been released TLP WHITE: Subject to standard copyright rules, TLP WHITE information may be distributed without restriction.

## Summary
The FBI assesses ransomware actors are very likely using significant financial events, such as mergers and acquisitions, to target and leverage victim companies for ransomware infections. Prior to an attack, ransomware actors research publicly available information, such as a victim’s stock valuation, as well as material nonpublic information. If victims do not pay a ransom quickly, ransomware actors will threaten to disclose this information publicly, causing potential investor backlash.

## Threat 
Ransomware actors are targeting companies involved in significant, time-sensitive financial events to incentivize ransom payment by these victims. Ransomware is often a two-stage process beginning with an initial intrusion through a trojan malware, which allows an access broker to perform reconnaissance and determine how to best monetize the access. However, while this malware is often mass distributed, most victims of trojans are not also victims of ransomware, indicating ransomware targets are often carefully selected from a pool based on information gleaned from the initial reconnaissance. During the initial reconnaissance phase, cyber criminals identify non-publicly available information, which they threaten to release or use as leverage during the extortion to entice victims to comply with ransom demands.  Impending events that could affect a victim’s stock value, such as announcements, mergers, and acquisitions, encourage ransomware actors to target a network or adjust their timeline for extortion where access is established. 

- In early 2020, a ransomware actor using the moniker “Unknown” made a post on the Russian hacking forum “Exploit” that encouraged using the NASDAQ stock exchange to influence the extortion process. Following this posting, unidentified ransomware actors negotiating a payment with a victim during a March 2020 ransomware event stated, “We have also noticed that you have stocks. If you will not engage us for negotiation we will leak your data to the nasdaq and we will see what's gonna (sic) happen with your stocks.”
- Between March and July 2020, at least three publicly traded US companies actively involved in mergers and acquisitions were victims of ransomware during their respective negotiations. Of the three pending mergers, two of the three were under private negotiations.
- A November 2020 technical analysis of Pyxie RAT, a remote access trojan that often precedes Defray777/RansomEXX ransomware infections, identified several keyword searches on a victim’s network indicating an interest in the victim’s current and near future stock share price. These keywords included 10-q<sup>1</sup>, 10-sb<sup>2</sup>, n-csr<sup>3</sup>, nasdaq, marketwired, and newswire.

***
<sup>1</sup> 10-Q is a quarterly report that must be submitted by all publicly traded companies disclosing relevant information regarding finances.
{: .fs-2}
<sup>2</sup> 10-SB was a filing form used to register the securities of small businesses who wished to trade on U.S. exchanges.
{: .fs-2}
<sup>3</sup> N-CSR is a form that registered management investment companies must file with the Securities and Exchange Commission within 10 days after a company disseminates annual and semi-annual reports to stockholders.
{: .fs-2}
***

- In April 2021, Darkside ransomware<sup>4</sup> actors posted a message on their blog site to show their interest in impacting a victim’s share price. The message stated, “Now our team and partners encrypt many companies that are trading on NASDAQ and other stock exchanges. If the company refuses to pay, we are ready to provide information before the publication, so that it would be possible to earn in the reduction price of shares.  Write to us in ‘Contact Us’ and we will provide you with detailed information.”

The FBI does not encourage paying a ransom to criminal actors. Paying a ransom emboldens
adversaries to target additional organizations, encourages other criminal actors to engage in
the distribution of ransomware, and/or may fund illicit activities. Paying the ransom also does
not guarantee that a victim’s files will be recovered. However, the FBI understands that when
businesses are faced with an inability to function, executives will evaluate all options to protect
their shareholders, employees, and customers. Regardless of whether you or your organization
have decided to pay the ransom, the FBI urges you to report ransomware incidents to your local
FBI field office. Doing so provides the FBI with the critical information they need to prevent
future attacks by identifying and tracking ransomware attackers and holding them accountable
under US law.

## Recommended
- Back-up critical data offline.
- Ensure copies of critical data are in the cloud or on an external hard drive or storage device.
- Secure your back-ups and ensure data is not accessible for modification or deletion from
the system where the original data resides.
- Install and regularly update anti-virus or anti-malware software on all hosts.
- Only use secure networks and avoid using public Wi-Fi networks.
- Use two-factor authentication for user login credentials, use authenticator apps rather than email as actors may be in control of victim email accounts and do not click on unsolicited attachments or links in emails.
- Implement least privilege for file, directory, and network share permissions. 

***
<sup>4</sup> Darkside is a ransomware-as-a-service variant, in which criminal affiliates conduct the attacks and the proceeds are shared with the ransomware developer(s). Darkside ransomware was used in the May 2021 Colonial Pipeline intrusion.
{: .fs-2}
***

- Review the following additional resources.
    - The joint advisory from Australia, Canada, New Zealand, the United Kingdom, and the United States on Technical Approaches to Uncovering and Remediating Malicious Activity provides additional guidance when hunting or investigating a network and common mistakes to avoid in incident handling.
    - The Cybersecurity and Infrastructure Security Agency-Multi-State Information Sharing & Analysis Center Joint Ransomware Guide covers additional best practices and ways to prevent, protect, and respond to a ransomware attack.
    - StopRansomware.gov is the U.S. Government’s official one-stop location for resources to tackle ransomware more effectively.

## Administrative Note
This product is marked TLP:WHITE. Subject to standard copyright rules, TLP:WHITE information may be distributed without restriction.  

For comments or questions related to the content or dissemination of this product, contact your local FBI field office.

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
