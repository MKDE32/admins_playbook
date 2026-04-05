# PROTOCOLS
## POP3
download from server to client

## IMAP
copy from server to client

## SMTP
sending emails

# SECURITY MEASURES
## DKIM
DomainKeys Identified Mail (DKIM): Helps to protect victims against phishing, email spoofing, and other email spam by preventing sender address forgery. DKIM attaches a header that contains a cryptographic private key to each email sent. This key is used to verify the identity of the sender and to detect if the email message was manipulated while in transit across the internet. Receiving email servers will usually designate emails without legitimate DKIM keys as spam. For more information and instructions to implement DKIM in Google Workspace, please see the article: Help prevent spoofing and spam with DKIM

## SPF
Sender Policy Framework (SPF): Used to control which domains, email servers, and IP addresses can send emails for an organization. SPF is examined by the receiving email servers to verify that the domains, email servers, and IP addresses from incoming emails are from approved senders. For more information and instructions to implement SPF in Google Workspace, please see the article: Help prevent spoofing and spam with SPF

## DMARC
Domain-based Message Authentication, Reporting, and Conformance (DMARC): Defines how the receiver should treat email messages depending on the results of DKIM and SPF checking. For more information and instructions to implement DMARC in Google Workspace, please see the article: Help prevent spoofing and spam with DMARC




