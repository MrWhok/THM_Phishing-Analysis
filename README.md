# THM_Phishing-Analysis

## Table of Contents
1. [Phishing Analysis Fundamentals](#phishing-analysis-fundamentals)

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
