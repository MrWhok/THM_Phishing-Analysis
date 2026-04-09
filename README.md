# THM_Phishing-Analysis

## Table of Contents
1. [Phishing Analysis Fundamentals](#phishing-analysis-fundamentals)
2. [Phishing Emails in Action](#phishing-emails-in-action)
3. [Phishing Analysis Tools](#phishing-analysis-tools)
4. [Phishing Prevention](#phishing-prevention)
5. [The Greenholt Phish](#the-greenholt-phish)

## Phishing Analysis Fundamentals
### The Email Address
1. Identify the domain used in the following email address: hatsalesman@tryhatme.com

    The answer is: `tryhatme.com`

### Email Delivery
1. Which protocol is responsible for sending an email from a client to a mail server?

    The answer is`SMTP`.

2. Which service is used to look up the recipient domain’s mail server?

    The answer is `DNS`.

3. Bob wants to access his email from multiple devices, including his phone and laptop. Which protocol should he use?

    The answer is `IMAP`.

### Email Headers
1. What is the full subject line of email1.eml?

    The answer is: `Help protect your budget by protecting your home`.

2. View the message source of email1.eml using Thunderbird in your VM. What the IP address listed as the X-Originating-Ip?

    The answer is: `43.255.56.161`.

### Email Body
1. Open up the email2.txt file to view the source of an attachment. What is the Content-Type of the attachment?

    The answer is: `application/pdf`.

2. What is the name of the attachment from the previous question?

    The answer is: `zmqpalgh.pdf`.

3. Decode the base64 string using either a PDF converter (opens in new tab) or CyberChef (opens in new tab). What is the hidden flag value?


    We can save the base 64 string to a file and then use this script to decode and convert to a PDF:

    ```python
    import base64

    with open("encoded.txt","r") as f:
        data = f.read()

    pdf = base64.b64decode(data)

    with open("zmqpalgh.pdf","wb") as f:
        f.write(pdf)
    ```
    The answer is: `THM{BENIGN_PDF_ATTACHMENT}`.

### Types of Phishing
1. Which reputable organization is being spoofed in this phishing attempt?

    The answer is: `Home Depot`.

2. What is the sender's email address?

    The answer is: `support@teckbe.com`.

3. Inspect the email message source. What is the defanged (opens in new tab) X-Originating-IP?

    The answer is: `103[.]234[.]236[.]83`.

4. Continue analyzing the email message source. Which mail server generated the Authentication-Results header?

    The answer is: `atlas102.free.mail.gq1.yahoo.com`.

### Conclusion
1. What attack, signified by the acronym BEC, uses a compromised email to trick employees into fraud?

    The answer is: `Business Email Compromise`.


## Phishing Emails in Action
### Cancel Your Order
1. Who is listed as the Merchant in the email body?

    The answer is: `Amazing Stuff`.

### Track Your Package
1. What root domain does the hyperlink in the above example point to? Be sure to defang the URL.

    The answer is: `devret[.]xyz`.

### Download Document Here
1. The attacker deployed a fake portal to capture and exfiltrate user credentials. What is this type of attack called?

    The answer is: `Credential Harvesting`.

### Your Account Is on Hold
1. What is the actual sender email address hidden behind the Netllx billing display name?

    The answer is: `z99@musacombi.online`.

### Your Recent Purchase
1. What does the acronym BCC stand for?

    The answer is: `Blind Carbon Copy`.

2. What is the file extension of the attachment?

    The answer is: `.dot`.

### Scheduled Shipment
1. What is the name of the executable that the Excel attachment attempts to run?

    The answer is: `regasms.exe`.


## Phishing Analysis Tools
### Email Header Analysis
1. Use Talos Reputation Center (opens in new tab) to look up malware-test.com. What is the web reputation assigned to this domain?

    The answer is: `Neutral`.

### Email Body Analysis
1. What command can you use in a Linux environment to obtain the SHA256 hash value of an attachment?

    The answer is: `sha256sum`.

### Using PhiShTool
1. According to the VirusTotal analysis from above, which vendor categorized the URLs as phishing?

    The answer is: `SafeToOpen`.

### Your Account Is on Hold 
1. What reputable brand is this email tailored to impersonate?

    The answer is: `Netflix`.

2. Based on the email headers, who is the intended recipient of this message?

    The answer is: `redacted@yahoo.com`.

3. In Thunderbird mail use View → Message Source. What is the Received: from IP address?

    The answer is: `10.197.37.234`.

4. Check out the Return-Path field in the message source. What would you consider a domain of interest based on this field?

    The answer is: `etekno.xyz`.

5. Investigate the UPDATE ACCOUNT NOW button. What is the shortened URL?

    The answer is: `https://t.co/yuxfZm8KPg?amp=1`.

### Update Payment Details
1. How does ANYRUN classify this suspected phishing email?

    The answer is: `Suspicious activity`.

2. What is the name of the PDF attachment?

    The answer is: `Payment-updateid.pdf`.

3. Investigate the email attachment. What is the SHA256 hash of the PDF file?

    The answer is `CC6F1A04B10BCB168AEEC8D870B97BD7C20FC161E8310B5BCE1AF8ED420E2C24`.

4. Check out the ANYRUN text report on the phishing email. Which IP address associated with the process AcroRd32.exe is flagged as malicious?

    The answer is: `2.16.107.24`.

5. Continue investigating the text report. Which Windows process is classed as Potentially Bad Traffic?

    The answer is: `svchost.exe`.

### Excel Executable
1. How does ANYRUN classify the .xlsx attachment?

    The answer is: `Malicious activity`.

2. What is the file name of the Excel attachment?

    The answer is: `CBJ200620039539.xlsx`.

3. Investigate the Excel attachment. What is the SHA256 hash value?

    The answer is `5f94a66e0ce78d17afc2dd27fc17b44b3ffc13ac5f42d3ad6a5dcfb36715f3eb`.

4. Check out the ANYRUN text report. What IP address is associated with the malicious domain biz9holdings.com?

    The answer is: `204.11.56.48`.

5. Which other domain is classified as malicious?

    The answer is: `findresults.site`.

6. What vulnerability does this malicious attachment attempt to exploit?

    The answer is: `cve-2017-11882`.


## Phishing Prevention
### Sender Policy Framework (SPF)
1. Based on TryHackMe's SPF record above, how many domains are authorized to send email on its behalf?

    The answer is: `3`.

2. What is the intended action of an email that returns a SoftFail verification result?

    The answer is: `Flag`.

### DomainKeys Identified Mail (DKIM)
1. Based on the sample header above, what is the reason for the permerror?

    The answer is: `no key for signature`.

### Domain-based Message Authentication, Reporting, and Conformance (DMARC)
1. Which DMARC policy provides the greatest amount of protection by blocking emails that fail the DMARC check?

    The answer is: `p=reject`.

### Secure/Multipurpose Internet Mail Extensions (S/MIME)
1. Which S/MIME component ensures that only the intended recipient can read the contents of an email message?

    The answer is: `Encryption`.

### Analyzing SMTP Responses
1. Which Wireshark filter can you use to narrow down your results based on SMTP response codes?

    The answer is: `smtp.response.code`.

2. How many packets in the capture contain the SMTP response code 220 Service ready?

    We can use this filter in Wireshark to find the answer: `smtp.response.code == 220`. The answer is: `19`.

3. One SMTP response indicates that an email was blocked by spamhaus.org. What response code did the server return?

    To solve this, we can search string that contains `spamhaus`. The answer is `553`.

4. Based on the packet from the previous question, what is the full Response code: message?

    The answer is: `Requested action not taken: mailbox name not allowed (553)`.

5. Search for response code 552. How many messages were blocked for presenting potential security issues?

    The answer is: `6`.

### Inspecting Email and Attachments
1. How many SMTP packets are available for analysis?

    We can use the filter `smtp` in Wireshark. The answer is: `512`.

2. What is the name of the attachment in packet 270?

    The answer is: `document.zip`.

3. According to the message in packet 270, which Host IP address is not responding, making the message undeliverable?

    The answer is: `212.253.25.152`.

4. By filtering for imf, which email client was used to send the message containing the attachment attachment.scr?

    We can use this filter to get the email that contains the attachment:
    
    ```
    imf contains "attachment.scr"
    ```
    The answer is: `Microsoft Outlook Express 6.00.2600.0000`.

5. Which type of encoding is used for this potentially malicious attachment?

    The answer is: `base64`.

### How Organizations stop Phishing
1. A security team wants to implement a control to detect hidden malware inside email attachments. They need a way to analyze suspicious files without risking infection on real systems. Which protective technique would allow them to observe a file's behavior safely?

    The answer is: `Sandboxing`.


## The Greenholt Phish
### A Message that doesn't Add Up
1. What is the Transfer Reference Number listed in the email's Subject line?

    The answer is: `09674321`.

2. What is the display name of the sender?

    The answer is: `Mr. James Jackson`.

3. Continue investigating the email headers. What is the sender's email address?

    The answer is: `info@mutawamarine.com`.

4. What email address will receive a reply to this email?

    The answer is: `info.mutawamarine@mail.com`.

5. Begin analyzing the message source. What is the originating IP address of this email?

    The answer is: `192.119.71.157`.

6. Investigate the IP address from the previous question. Who is the owner of the originating IP?

    We can use [this](https://whatismyipaddress.com/ip/192.119.71.157) website and type the IP address to find the answer. The answer is: `Hostwinds LLC`.

7. Run an SPF record check on the Return-Path domain identified in the email headers. What is the full SPF record for this domain?

    We can copy the Return-Path domain, `mutawamarine.com`, and use [this](https://dmarcian.com/spf-survey/) website to check the SPF record. The answer is: `v=spf1 include:spf.protection.outlook.com -all`.

8. Perform a DMARC lookup for the Return-Path domain found in the email headers. What is the complete DMARC record for this domain?

    We can copy the Return-Path domain, `mutawamarine.com`, and use [this](https://dmarcian.com/domain-checker/) website to check the DMARC record. The answer is: `v=DMARC1; p=quarantine; fo=1`.

9. What is the file name of the attachment found in the email?

    The answer is: `SWT_#09674321____PDF__.CAB`.

10. Download the attachment to your virtual environment. Using the sha256sum command, what is the SHA256 hash of the file?

    The answer is `2e91c533615a9bb8929ac4bb76707b2444597ce063d84a4b33525e25074fff3f`.

11. Investigate the file hash from the previous question using VirusTotal (opens in new tab). What is the attachment's file size in KB (e.g., 122.31 KB)?

    We can copy the hash value and use [this](https://www.virustotal.com/gui/home/search) website to check the file size. The answer is: `400.26 KB`.

12. Continue your research on the file. What is the actual file type of the attachment?

    The answer is: `RAR`.



