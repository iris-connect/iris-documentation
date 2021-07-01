# Get a certificate to connect your app to IRIS
To get a certificate that allows you to connect your app to IRIS you need to go through the following steps:
1. Request the certificate from the IRIS rollout team
2. Proof your identity
3. Proof your right to represent your organization
4. Accept some terms and conditions

## Request the certificate
To request the certificate, you, the certificate applicant, must email the IRIS rollout team (rollout@iris-gateway.de). We recommend securing all email communication using [PGP or S/MIME (TODO: upload)]().

The certificate applicant is always a natural person who submits a certificate request either on behalf of himself or on behalf of a legal entity for which he is authorized to represent.

Please provide this information in your email:
1. A certificate request as a CSR file. See [here](https://github.com/iris-connect/iris-documentation/blob/main/connect_your_app_to_IRIS/technical_details/app_onboarding.md) how to generate it.
2. Your personal identification information (full name, birthdate and address according to your ID card, passport or residence permit)
3. If you request on behalf of a legal entity (e.g., GmbH, e.V., Ltd.), you must proof your right to represent (Vertretungsberechtigung). Therefore, you can use this [power of attorney template (TODO: create template)]( ). It must be signed by an individual who is authorized to represent the organization and whose identity can be verified and validated based on publicly available information (see below).

## Validation
The IRIS CA operator must validate the claimed identity and, if applicable, your right to represent.

### Validate your right to represent
The IRIS CA operator must be able to validate your right to represent on the basis of publicly available information. This includes public registers, e.g. commercial register (Handelsregister) or register of associations (Vereinsregister). If you decide to file a power of attorney, It must be signed by a member of your organization who is authorized to represent and whose identity can be verified and validated based on publicly available information. Alternatively, the IRIS CA operator an call your organization to get a verbal confirmation of your right to represent as stated in your request.

### Validate your identity
You will receive an email asking you to prove your legal identity. The validation will be carried out by our partner **TODO: FILL_NAME_HERE**. You can choose one of these alternatives:
1. Video-Ident or
2. the eID function of your ID card (see eID feature of German national ID card [English](https://www.personalausweisportal.de/Webs/PA/EN/citizens/electronic-identification/electronic-identification-node.html) / [German](https://www.personalausweisportal.de/Webs/PA/DE/buergerinnen-und-buerger/online-ausweisen/das-brauchen-sie/das-brauchen-sie-node.html))

If you or your organisation own a TLS certificate with Extended Validation (OV/EV) trust level, you can shortcut the next identity validation step (Video-Ident/eID-Ident). See below for details.

Next, we will email you a commitment form. Please click the link to digitally sign it. We use [qualified electronic signatures](https://en.wikipedia.org/wiki/Qualified_electronic_signature) (QES) for digital signing. QES is considered as digital equivalent to handwritten signatures according to EU regulations. After you have signed, the form will be automatically sent back to the IRIS CA operator.

### Receive your certificate
As soon as the validation has been completed, you will receive your certificate via signed email (also encrypted if you provided us a PGP key or S/MIME certificate). 
At the same time, the IRIS rollout team will activate your certificate. This is done by publishing the public key in the service directory (public-key pinning). 
We ask for your understanding if there are some hours time difference between both processes.

#### Proof-of-Identity Shortcut
If you or your organization have a TLS certificate with the Extended Validation (EV) trust level, you can skip the Video-Ident/eID-Ident step of the identity verification process. To do this, you must include the domain of the EV certificate in the CSR. Note that you do not need to own/control a domain per se to use IRIS. However, if you have one, it can be used for this shortcut.

An IRIS CA operator verifies that you control the domain. You can choose to do this either by email or DNS.

1. Validation by email:
The IRIS rollout team sends emails to several typical email addresses for the specified domain:
    * administrator@your_domain_name
    * hostmaster@your_domain_name
    * postmaster@your_domain_name
    * webmaster@your_domain_name
    * admin@your_domain_name
2. Validation by DNS:  
The IRIS rollout team provides you with a key-value pair that you set up as DNS TXT record for the domain. This record serves as proof of domain control.

In both cases, report back to the IRIS rollout team so that it can check the DNS record, or email code, respectively.

