

# How to connect your App to IRIS


In this document we describe how apps can be connected to the IRIS system.  


## Overview

The IRIS System consists of different actors that form trust relationships with each other based on certificates. These actors are 1) IRIS Central services 2) Contact Tracing Applications (you) and 3) Health Departments. Actors use the [IRIS endpointserver](https://github.com/iris-gateway/eps) in order to exchange messages with other actors. Each actor is registered in the public IRIS service directory alongside with its corresponding role on the IRIS system.

Please find below and overview of the IRIS system and its actors as well as the flows that are relevant for your application. 

![Overview IRIS System](iris-system.jpg)

|Step|Description|
|-|-|
|1|You need to send a certificate signing request (csr) to the [IRIS rollout team](mailto:rollout@iris-gateway.de). The rollout team will provide you with a certificate in return. You need to configure your EPS to use that certificate.|
|2|The IRIS rollout team registers your app and the endpoint domain in the service direcory.|
|3|Your app pushes the locations for those it is responsible for into the central locations service. This is a frequent process and depends on the lifecycle of the locations that are managed within by app|
|4|The health authority employees can use the IRIS client (having ints own EPS) in order to search for locations.|
|5|The IRIS client connects to your app through the EPS layer and requests guest lists for a specific date and time. In order to know the endpoint IRIS internally keeps a record of which location is owned by which app. Your app returns the contact information using EPS.|



## Request a certificate

Generate your certificate signing request 

    O="COSYNUS GmbH"
    ST="Europaplatz 5"
    L="64293 Darmstadt"
    C="DE"
    OU="IT"
    CN="smartmeeting"
    # using less than 1024 here will result in a TLS handshake failure in Go
    # using less than 2048 will cause e.g. 'curl' to complain that the ciper is too weak
    LEN="2048"


    openssl genrsa -out "${cert}.key" 2048;
  	openssl rsa -in "${cert}.key" -pubout -out "${cert}.pub";
  	openssl req -new -sha256 -key "${cert}.key" -subj "/C=${C}/ST=${ST}/L=${L}/O=${O}/OU=${OU}/CN=${cert}" -addext "subjectAltName = DNS:${cert},DNS:*.${cert}.local" -out "${cert}.csr";

with your information in subject and your app name as ${cert}. Please use your app name as CN (for example CN=smartmeeting). Don't use spaces. 
 
Send the .csr to [IRIS rollout team](mailto:rollout@iris-gateway.de) and get your .crt file back from us.
  	

## Install and configure EPS

You can start a local eps with

    docker run -exp-v [your-local-settings-path]:/app/settings -e EPS_SETTINGS=settings/staging/roles/[yourapp] luckylusa/iris-eps-bundle:0.0.1-stable --level trace server run
 
`[yourapp]` corresponds to the app name you chose for CN in your certificate. 

### Config files and certificates

ToDo

## Push your locations to IRIS

Sending messages to IRIS is done with JSON-RPC. 

    {
        "method": "[destination-identifier].[methodname]", 
        "id": "1", 
        "params": {
            "param1": "test"
        }, 
        "jsonrpc": "2.0"
    }
    
You can find the specification of the respective methods and destinations [here](#destinations-and-methods).

## Destinations and methods

### Location search index

Location search index can be reached at `ls-1`.

Possible methods and their structure are

#### postLocationsToSearchIndex

##### Request

Example parameters:

    "params": {
            "locations": [
                {
                    "id": "5eddd61036d39a0ff8b11fdb",
                    "name": "Restaurant Alberts",
                    "contact": {
                        "officialName": "Meine RestoGruppe GmbH",
                        "representative": "Max Mustermann",
                        "address": {
                            "street": "Türkenstr. 7",
                            "city": "München",
                            "zip": "80333"
                        },
                        "email": "covid@restaurant.de",
                        "phone": "0151 47110815"
                    }                
                }
            ]
        }
        
| Parameter | Description | Annotations |
| --- | --- | --- |    
| `locations` | array of locations | 

Location parameters:

| Parameter | Description | Annotations |
| --- | --- | --- |    
| `id` | your unique location id | Identifies the location in your system. Will be included in incoming requests 
| `name` | location friendly name | You could also split your clients sites here. Example: client has site "Hauptstrasse" and "Kaiserstrasse" could be split in two locations with their own location id.
| `contact` | contact information | see below

Contact parameters:

| Parameter | Description | Annotations |
| --- | --- | --- |    
| `officialName` | locations official name |  
| `representative` | locations representative | 
| `email` | email | 
| `phone` | phone number

##### Response 

    "result": {
            "_": "OK"
        },

`OK` if successful. Errormessages to be done.

#### getProviderLocations

Example parameters:
    
    "params": {                  
    }

| Parameter | Description | Annotations |
| --- | --- | --- |    
| `providerId` | your unique ProviderId | Caution: this will change and will not be required in the future.

##### Response 

    "result": {
            "_": [
                {
                    "id": "5eddd61036d39a0ff8b11fdb",
                    "name": "Restaurant Alberts"
                }
            ]
    }

Array of `id` and `name` pairs, where id is your unique identfier and `name` the locations friendly name. Errormessages to be done. 

#### deleteLocationFromSearchIndex

Example parameters:

    "params": {
        "locationId":"5eddd61036d39a0ff8b11fdb"
    }

| Parameter | Description | Annotations |
| --- | --- | --- |    
| `locationId` | your internal location identifier | | 

##### Response 

    "result": {
            "_": "OK"
        },

`OK` if successful. `NOT FOUND` if location did not exist. Errormessages to be done.

## Process IRIS Client data requests

ToDo
## Send data submissions

ToDo

## Changelog

### [0.0.2] - 2021-05-08

#### Added
- Overview drawing including steps and descriptions.
- Structure for data requests and data submissions.

### [0.0.1] - 2021-05-04

#### Added
- Initial version of the onboarding document
- Adding locations to search index 
