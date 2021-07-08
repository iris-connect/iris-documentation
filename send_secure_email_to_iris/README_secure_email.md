# Send and receive secure emails

You can send and receive signed and encrypted emails with the IRIS team. We recommend you to use this option.

## Send encrypted mails
To send encrypted emails to IRIS, you can use either PGP or S-MIME. Please download and use our [PGP keys](https://github.com/iris-connect/iris-documentation/blob/main/send_secure_email_to_iris/pgp/) or [S/MIME certificates](https://github.com/iris-connect/iris-documentation/blob/main/send_secure_email_to_iris/smime/).

## PGP
The manual of your email client will tell you how to import/download and use PGP keys.

## S/MIME
Currently, our S/MIME certificates are issued by our self-sigend IRIS certificate authority (CA).  
Therefore, you will also need to import the IRIS CAs to your system or email client, respectively, and mark them trusted for email communication. 
Here you can get our [CA bundle](https://github.com/iris-connect/iris-documentation/blob/main/send_secure_email_to_iris/smime/).
The manual of your email client will tell you how to import and use the CAs and S/MIME certificates. 
However, if you have no experience with S/MIME and CAs, using PGP may be the easier option for you.

## Receive encrypted mails from the IRIS team
To receive encrypted emails, send your PGP public key or S/MIME certificate as an attachment to [rollout@iris-gateway.de](mailto:rollout@iris-gateway.de?subject=My%20PGP%20key%20or%20S/MIME%20certificate). 
The email address you use must be included in the PGP key or S/MIME certificate. The sender address of the email will be ignored. You will receive an email confirmation.
