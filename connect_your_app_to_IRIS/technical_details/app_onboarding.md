

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

---

### Prerequisites

This guide will show step by step technically integrating an app to IRIS connect.
- [Certificate generation and enrollment](#1-certificate-generation-and-enrollment)
- [Local deployment of the EPS](#2-install-and-configure-eps)
- [General usage of the EPS](#3-interacting-with-eps)
- [Services and Methods of the EPS](#32-destinations-and-methods)
- [Use EPS to post locations to the IRIS connect search index](#41-location-search-index)
- [Listen to data requests of the health department submitted to the EPS](#42-process-iris-client-data-requests)
- [Transmit requested data to the health department using EPS](#43-send-data-submissions)

You need to open port 4444 for incoming connections. 

The EPS installed on your server needs to be reached on port 4444, this will not be changed (yet).

You will need openssl to create the certificate and preferably docker to run the EPS.

---

## 1 Certificate Generation and Enrollment

A unique certificate for your app is needed to achieve trust for communication reaching out from your local EPS to remote EPS of IRIS central services or IRIS clients.

The certificate is signed by IRIS connect with a root certificate. The root certificate itself delivers trust for the local EPS for incoming communication.

### 1.1 Generate Certificate Signing Request

Generate your certificate signing request (csr) using openssl for the IRIS Connect staging server.
When switching to production, you will need a separate certificate. We skip this for now, but we will provide it later in this documentation as soon as we set IRIS connect to productive use.

Please use your app name as CN (for example CN=smartmeeting). *Don't use spaces*.

    O="COSYNUS GmbH"
    ST="Europaplatz 5"
    L="64293 Darmstadt"
    C="DE"
    OU="IT"
    CN=[yourappname]
    # using less than 1024 here will result in a TLS handshake failure in Go
    # using less than 2048 will cause e.g. 'curl' to complain that the ciper is too weak
    LEN="2048"


    openssl genrsa -out "[yourappname].key" 2048;
  	openssl rsa -in "[yourappname].key" -pubout -out "[yourappname].pub";
  	openssl req -new -sha256 -key "[yourappname].key" -subj "/C=${C}/ST=${ST}/L=${L}/O=${O}/OU=${OU}/CN=${CN}" -addext "subjectAltName = DNS:[yourappname],DNS:*.[yourappname].local" -out "[yourappname].csr";

### 1.2 Request the Certificate

Send the .csr and your domain to [IRIS rollout team](mailto:rollout@iris-gateway.de) and get your .crt file back from us.

Example
    
    Hi IRIS Team,

    I provide the csr for api.test.perkiot.com:4444 (staging).
    Prod is at api.perkiot.com:4444.

    BR
    Mic

For production use it will be neccessary to generate a different csr, and that will be done after integration; the production uri is not needed in this step, just for information (and the IRIS team can maybe do some preparation).

## 2 Install and configure EPS

The EPS (IRIS EndPointService) does all the magic in a black box:
- encryption of the data send to the IRIS clients requesting the contact lists
- ensure trust for IRIS and your app
- dealing with p2p networking to eliminate bottlenecks

To be able to act, the EPS needs to be configured and trusted, which means it needs the trusted and unique certificate signed from the [csr](#11-generate-certificate-signing-request) you have send to IRIS team, and it must be made known to IRIS, that is the step IRIS team does with the provided URI before issuing the certificate.

### 2.1 Artifacts needed to start

You need the following:
- a local settings directory
- the IRIS staging-root.crt
- your [certificate](#11-generate-certificate-signing-request)
- docker image inoeg/eps

### 2.2 Local Settings

The settings folders in the IRIS connect documentation repository below [eps-config](./technical_details/eps-config) must be copied to your own server.

We show two different possibilities to get your local settings done: on [Linux command line](#221-linux-command-line) or with your prefered [Desktop GUI](#222-desktop-usage).

#### 2.2.1 Linux Command Line

We could set some helpful environment variables here to use it in the following steps, change the base dir of $SETTINGS_PATH to match your needs:

    export APP_NAME="[yourapp]"
    export APP_ENDPOINT="http://[your-host]:[your-port]/[your-endpoint]"
    export SETTINGS_PATH="/data/eps/settings"
    mkdir -p $SETTINGS_PATH

Where:
- the APP_NAME is the name provided by you as CN in the [certificate signing request](#11-generate-certificate-signing-request)
- the APP_ENDPOINT is the api endpoint of your app that will be called by EPS to submit data requests.

**Be aware that you have to ensure to open this api endpoint for your local EPS only!**

There are only two relevant files, and you can copy them one by one and put them in the corresponding folder.

    mkdir -p "$SETTINGS_PATH/staging/roles/$APP_NAME"

    wget https://raw.githubusercontent.com/iris-connect/iris-documentation/main/connect_your_app_to_IRIS/technical_details/eps-config/settings/staging/roles/yourapp/001_default.yml -P "$SETTINGS_PATH/staging/roles/$APP_NAME"

    mkdir -p "$SETTINGS_PATH/staging/certs"
    
    wget https://raw.githubusercontent.com/iris-connect/iris-documentation/main/connect_your_app_to_IRIS/technical_details/eps-config/settings/staging/certs/staging-root.crt

The certificate issued by IRIS based on your signing request and the corresponding key must be stored in the certs folder.

    mv /path/to/your/cert/$APP_NAME.crt "$SETTINGS_PATH/staging/certs"
    mv /path/to/your/cert/$APP_NAME.key "$SETTINGS_PATH/staging/certs"

The settings file must be adapted according to this document and the comments in the respective files. If you followed the instructions exporting the variables, you can just do it with this command:

    envsubst < 001_default.yml > "$SETTINGS_PATH/staging/roles/$APP_NAME/001_default.yml"

    rm 001_default.yml # cleanup template

Well, you are ready to [start your EPS](#23-start-your-eps), skip the desktop usage section.

#### 2.2.2 Desktop usage

To use a browser for download, you can get a [zip compressed archive here](https://downgit.github.io/#/home?url=https://github.com/iris-connect/iris-documentation/tree/main/connect_your_app_to_IRIS/technical_details/eps-config/settings) and unzip it to the folder $SETTINGS_PATH.

The [settings yaml file](./technical_details/eps-config/settings/staging/roles/yourapp/001_default.yml) is placed in a directory naming your app, so be aware to change it accordingly to something like "/data/eps/settings/staging/roles/$APP_NAME"

The IRIS certificate staging-root.crt is available in [certs directory](.technical_details/eps-config/settings/staging/certs) and will be in your certs dir at the right place if folder structure was copied from there.

The certificate issued by IRIS based on your signing request and the corresponding key must be stored in the certs folder.

The settings file must be adapted according to this document and the comments in the respective files. Search and replace $APP_NAME with your app's name and $APP_ENDPOINT with the endpoint address of your app, that is (or will be) open for requests from your local EPS.

    name: $APP_NAME
    directory:
    type: api
    settings:
        jsonrpc_client:
        tls:
            certificate_file: "$DIR/../../certs/$APP_NAME.crt"
            key_file: "$DIR/../../certs/$APP_NAME.key"
    [...]
    - name: main JSON-RPC client # creates outgoing JSONRPC connections to deliver and receive messages
        type: jsonrpc_client
        settings:
        endpoint: http://$APP_ENDPOINT
    - name: main gRPC client
        type: grpc_client
        settings:
        tls:
            ca_certificate_files: [ "$DIR/../../certs/staging-root.crt" ]
            certificate_file: "$DIR/../../certs/$APP_NAME.crt"
            key_file: "$DIR/../../certs/$APP_NAME.key"

Service directory location will be set in your settings 001_default.yml - currently we provide a staging environment service-directory. When production is available, you will need to generate new certificates and change the service-directory uri. Below is the URI for staging as used in the provided settings.

    directory:
      settings:
        endpoints: [ "https://iris.staging.iris-gateway.de:3322/jsonrpc" ] 
        
### 2.3 Start your EPS

The settings folder is then referenced in the docker call as ``$SETTINGS_PATH`` as an absolute path. If you are on Linux command line and defined it above, you could simply use the statement as is.

You can start a local eps with

    docker run --name iris-eps --expose 5556 --expose 4444 -p 5556:5556 -p 4444:4444 -v "$SETTINGS_PATH:/app/settings" -e EPS_SETTINGS="settings/staging/roles/$APP_NAME" inoeg/eps:v0.1.4 --level trace server run
 
Again, `$APP_NAME` corresponds to the app name you chose for CN in your certificate. 

Port 4444 is mandatory for staging environment. You can change port 5556 to your needs. Requests of your app, that shall reach out to IRIS Connect, will then be sent to `POST https://localhost:5556/jsonrpc`.

## 3 Interacting with EPS

The EPS is now locally reachable for your app, and it is publically reachable for IRIS Connect.
Let's test, if we are able to reach IRIS Connect from EPS.

### 3.1 Sending messages

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

To test, we will simply send a test location to IRIS staging:

    curl --header "Content-Type: application/json" --request POST --insecure --data '
    {
        "method":"ls-1.postLocationsToSearchIndex",
        "id": "1",
        "params": {
            "locations": [
                {
                    "id": "1abc",
                    "name": "Visits Test"
                }
            ]
        },
        "jsonrpc": "2.0"
    }
    ' https://localhost:5556/jsonrpc

We should get 

    {
        "jsonrpc" : "2.0",
        "result" : "OK",
        "id" : "1"
    }

It is important to know, what is going wrong if you won't get this response. If you post your request to a wrong endpoint, you would just get a "message":"not found". If the port 5556 is not bound to the eps container, you will get a "connection refused".

| cURL result | Possible cause | Ckecks to perform |
|-|-| - |
| Client sent an HTTP request to an HTTPS server. | You called the endpoint at http:// instead of https:// | Ckeck the address in cURL command and options you used. |
| Connection refused | The EPS is not listening on the URI or port of the request. | Ckeck the address in cURL command. Are you running the command from localhost - the docker host, or do you need to address an IP address in your network? Is there a firewall blocking the port? Is the EPS running - check it with docker ps, and check the logs. |
| "message":"not found" | You addressed wrong endpoint | If you address https://localhost:5556/ (without endpoint address jsonrpc) you will get this result. |
| {"jsonrpc":"2.0","error":{"code":-32603,"message":"internal error"},"id":"1"} | There is a bug in EPS or your configuration is incorrect. | Check the settings yml, try another EPS version. |

This list is propably not complete. Especially internal errors will have many possible causes. In case you get some internal errors, please check twice if your settings are correct, the EPS is running in level trace and have a look on log messages.

We will update the list of possible errors as they come around.

### 3.2 Destinations and methods

|Destination|Methodname|Annotations|
|-|-|-|
| ls-1 | [postLocationsToSearchIndex](#411-postlocationstosearchindex) | Publish managed locations to IRIS connect, for which health departments may request contact data.
| ls-1 | [getProviderLocations](#412-getproviderlocations) | Verify which locations managed by your app are published to IRIS connect.
| ls-1 | [deleteLocationFromSearchIndex](#413-deletelocationfromsearchindex) | Remove a managed location if the location canceled using your app etc.
| - | [createDataRequest](#42-process-iris-client-data-requests) | This method has to be an endpoint of your app to receive the details for an data request.
| hd-xyz | [submitGuestList](#431-send-data-from-app-backend) | After getting a data request, the data is send to the hd-endpoint given in _client.name in the request.


## 4 Integration of EPS Methods in your App

As described above, you have to 
- publish locations managed by your app
- receive data requests
- submit data

### 4.1 Location search index

Location search index can be reached at `ls-1`.

### 4.1.1 postLocationsToSearchIndex

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

#### 4.1.2 getProviderLocations

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

#### 4.1.3 deleteLocationFromSearchIndex

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

## 4.2 Process IRIS Client data requests

You need to provide a json-rpc endpoint on your server. The exact endpoint can be configured in your EPS configuration file. 
    
    - name: main JSON-RPC client # creates outgoing JSONRPC connections to deliver and receive messages
        type: jsonrpc_client
        settings:
          endpoint: http://[your-host]:[your-port]/[your-endpoint]
          
To receive incoming DataRequests, you need to implement a method `createDataRequest` on your Endpoint. 

The method has to accept the following paramters:

createDataRequest parameters:

| Parameter | Description | Annotations |
| --- | --- | --- |    
| `_client` | Calling EPS details |  
| `dataRequest` | DataRequest details |

_client object:

| Parameter | Description | Annotations |
| --- | --- | --- |    
| `name` | Calling eps | You will use this name to reach the endpoint for data submissions  

dataRequest object:

| Parameter | Description | Annotations |
| --- | --- | --- |    
| `start` | Start of requested time period | 
| `end` | End of requested time period | You will use this name to reach the endpoint for data submissions  
| `requestDetails` | Additional message (optional) | May contain additional information about the request   
| `dataAuthorizationToken` | Identifies the request to the health department | Used in submission to ensure that the data has been requested by the HD.   
| `connectionAuthorizationToken` | Identifies the connection to public proxy | Will be necessary in the future to be able to send submissions from the browser.
| `locationID` | Your location identifier | The identifier you used when creating the location.

Response:

| Parameter | Value | 
| --- | --- |  
| `_` | ``OK`` | 

The request can be saved and edited locally. The functions for transmitting the data to the health authorities are next on the roadmap.

## 4.3 Send data submissions

There are two ways to submit data to IRIS. The two ways result from the two different types of data management. Apps that can provide data unencrypted in the backend can send data directly to IRIS via EPS from the backend. If the user data must first be decrypted by the operator or another authority in the browser, it can then be transmitted directly from the browser via end-to-end encryption.

### 4.3.1 Send data from app backend

The data is sent to the custom EPS via JSON-RPC. The method name used is `[hdEndpoint].submitGuestList`. `[hdEnpoint]` corresponds to _client.name from the received DataRequest.

    {
    	"dataAuthorizationToken": "2edd34d6-bc7b-11eb-8529-0242ac130003",
    	"guestList": {
    		"dataProvider": {
    			"name": "SmartMeeting",
    			"address": {
    				"street": "Europaplatz",
    				"houseNumber": "5",
    				"zipCode": "64293",
    				"city": "Darmstadt"
    			}
    		},
            "startDate": "2021-05-18T10:00:00.000Z",
            "endDate": "2021-05-19T10:00:00.000Z",
            "additionalInformation": "",
    		"guests": [
    			{
    				"firstName": "Hans",
    				"lastName": "Müller",
    				"sex": "UNKNOWN",
    				"email": "p5o50dtktj@temporary-mail.net",
    				"phone": "0151 47110815",
    				"mobilePhone": "0151 47110815",
    				"address": {
    					"street": "Lietzensee-Ufer",
    					"houseNumber": "75",
    					"zipCode": "01657",
    					"city": "Meißen"
    				},
    				"attendanceInformation": {
    					"attendFrom": "2021-03-28T19:21:28.071Z",
    					"attendTo": "2021-03-28T19:21:28.071Z",
    					"additionalInformation": "Tisch 4"
    				}
    			}
    		]
    	}
    }
      
Parameters:

| Parameter | Description | Annotations |
| --- | --- | --- |    
| `dataAuthorizationToken` | Authorizes data submission | 
| `guestList` | Guest list information |

GuestList object:

| Parameter | Description | Required | Annotations |
| --- | --- | --- | --- |   
| `startDate` | GuestList starts | true |   
| `endDate` | GuestList ends | true |
| `additionalInformation` | Additonial information | true | Can be left empty for now - is not displayed 
| `dataProvider` | DataProvider object | true |
| `guests` | Guest object | true | 

DataProvider object:

| Parameter | Description | Required | Annotations |
| --- | --- | --- | --- |   
| `name` | Your name | true |   
| `address` | Address object | true |

Guest object:

| Parameter | Description | Required | Annotations |
| --- | --- | --- | --- |   
| `firstName` | First name | true |   
| `lastName` | Last list | true |
| `sex` | Sex | false | `[ MALE, FEMALE, OTHER, UNKNOWN ]` 
| `email` | E-Mail | false |
| `phone` | Phone number | false |
| `mobilePhone` | Mobile number | false |
| `address` | Address object | false |
| `attendanceInformation` | Attendance object | true |

Address object:

| Parameter | Description | Required | Annotations |
| --- | --- | --- | --- |       
| `street` | Street | false |   
| `houseNumber` | House number | false |
| `zipCode` | Zip code | false | 
| `city` | City | false |

AttendanceInformation object:

| Parameter | Description | Required | Annotations |
| --- | --- | --- | --- |       
| `attendFrom` | Attend from | true |   
| `attendTo` | Attend to | true |
| `additionalInformation` | Additional attendance information | false | For example table or area 

## 5 Test your implementation

To test your implementation, visit https://iris.staging.iris-gateway.de 

You can find the password and access data in the slack channel.

There you should find your pushed locations in the search when you start a new event tracking. If you send the request, you should receive a data request. 

## Changelog

### [0.0.5] - 2021-06-02

#### Changed
- Submit data when accessible in backend
- New eops image version 

### [0.0.4] - 2021-05-20

#### Added
- Submit data when accessible in backend

#### Changed
- Docker command with new eps version

### [0.0.3] - 2021-05-20

#### Added
- Receiving data requests
- Improved setup instructions
- Test your implementation

### [0.0.2] - 2021-05-08

#### Added
- Overview drawing including steps and descriptions.
- Structure for data requests and data submissions.

### [0.0.1] - 2021-05-04

#### Added
- Initial version of the onboarding document
- Adding locations to search index 
