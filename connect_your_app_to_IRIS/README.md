# IRIS Connect for App Providers

In this document we describe what app providers have to do to be connected to the IRIS connect system.

IRIS stands for "Integration of Remote systems into Infection control Software".
- IRIS connect is the platform solution enabling this integration.
- Remote systems are the apps providing personal contact data or other functionality supporting infection control processes.
- Infection control software like SORMAS is used by the health departments.

## Prerequisites

In order to be connected to IRIS, there are technical and non-technical things to do. Both can be performed in parallel or sequentially, following the ability of the app provider.

If the provider has separate staff for development and business administration, the IRIS team encourages the provider to run both processes in parallel to save time.

### Non-Technical Workstream

The non-technical workstream consists of documentation and commitment. It is a business adminstration topic. 

- Consent to the General Terms and Conditions of IRIS
- Submit documentation about your app to IRIS
  - Data Privacy Concept
  - IT-Security Concept
  - Technical Whitepaper
  - Code of Conduct
 
Well, ok, parts of the documentation topic IS technical... 

Details to this workstream are explained in the [documentation readme](./Connect_App_to_IRIS.md).

### Technical Workstream

The technical workstream consists only of two parts:
- Make your local EPS up and running
- Connect your App to EPS

For those that can't wait starting, just follow the [integration readme](./technical_details/app_onboarding.md).

The EPS (IRIS EndPointService) does all the magic in a black box:
- encryption of the data send to the IRIS clients requesting the contact lists
- ensure trust for IRIS and your app
- dealing with p2p networking to eliminate bottlenecks

To be able to act, the EPS needs to be configured and trusted, which means it needs a trusted and unique certificate, and it must be registered in IRIS.

How to achieve that is documented step by step in the [integration readme](./technical_details/app_onboarding.md).

## Conclusion

All tasks above shall take less than a week in total, if you can spent your working time exclusively.

Please keep in mind, that IRIS capitalizes Privacy and Security. Your documentation shall be honest and your app shall be as secure as possible. IRIS in total is as secure as the weakest app in its network.

Well, no, there are some tricks to be more secure than the weakest, but you got the idea, right?