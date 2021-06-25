# Work in Progress: Digitales Wartezimmer

Bitte beachten: das ist ein erster Entwurf.

## Initiieren des Requests ans digitale Wartezimmer

Damit Nutzer:innen Kontakttagebücher über das Digitale Wartezimmer ans Gesundheitsamt senden können, generieren wir im Gesundheitsamt Client einen Link zum digitalen Wartezimmer.

    https://[URL DW]/[Pfad DW]/[IRIS-Daten]

Die IRIS Daten sind Base64 codiert und enthalten einen JSON Payload.

    {
        "d": "dataAuthorizationToken - identifiziert die Daten",
        "c": "connectionAuthorizationToken - die URL zum Proxy",
        "p": "Die PLZ des Gesundheitsamts"
    }
    
## Beantworten des Requests

Der Request kann über einen JSON-RPC Call beantwortet werden.

Dazu wird ein POST an folgendes URL Schema abgesetzt.

    https://[connectionAuthorizationToken]:[Port]/data-submission-rpc
    
Der Port variiert je nach Staging / Production. ToDo: Port ins Dokument aufnehmen.

Payload des JSON-RPC Calls:

     {
     	"jsonrpc": "2.0",
     	"method": "submitContactData",
     	"params": {
     		"contacts": {
     			"contactPersons": [
     				{
     					"firstName": "string",
     					"lastName": "string",
     					"dateOfBirth": "2021-06-11",
     					"sex": "UNKNOWN",
     					"email": "user@example.com",
     					"phone": "string",
     					"mobilPhone": "string",
     					"address": {
     						"street": "string",
     						"houseNumber": "string",
     						"zipCode": "string",
     						"city": "string"
     					},
     					"workPlace": {
     						"name": "string",
     						"pointOfContact": "string",
     						"phone": "string",
     						"address": {
     							"street": "string",
     							"houseNumber": "string",
     							"zipCode": "string",
     							"city": "string"
     						}
     					},
     					"contactInformation": {
     						"firstContactDate": "2021-06-11",
     						"lastContactDate": "2021-06-11",
     						"contactCategory": "HIGH_RISK",
     						"basicConditions": "string"
     					}
     				}
     			],
     			"startDate": "2021-06-11",
     			"endDate": "2021-06-11"
     		},
     		"events": {
     			"events": [
     				{
     					"name": "string",
     					"phone": "string",
     					"address": {
     						"street": "string",
     						"houseNumber": "string",
     						"zipCode": "string",
     						"city": "string"
     					},
     					"additionalInformation": "string"
     				}
     			],
     			"startDate": "2021-06-11",
     			"endDate": "2021-06-11"
     		},
     		"dataProvider": {
     			"firstName": "string",
     			"lastName": "string",
     			"dateOfBirth": "2021-06-11"
     		}
     	},
     	"id": 1
     }

Die Parameter bzw. deren Daten könnten sich je nach Implementierung noch etwas ändern.
