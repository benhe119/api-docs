# Chapter 1

PolyLogyx REST API allows developers to use a programming language of their choice to integrate with
the headless PolyLogyx server. The REST APIs provide the means to configure and query the data from
the fleet manager. The APIs also allow an openc2 orchestrator to get visibility into endpoint data and
activities, which can then be used to craft an openc2 action.

All payloads are exchanged over REST and use the JSON schema.

## REST Based API

* Makes use of standard HTTP verbs e.g. GET, POST, DELETE
* Uses standard HTTP error responses to describe errors
* Authentication provided using API keys in the HTTP Authorization header
* Requests and responses are in JSON format.

## Versioning

The PolyLogyx API is a versioned API. We reserve the right to add new parameters, properties,
or resources to the API without advance notice. These updates are considered non-breaking
and the compatibility rules below should be followed to ensure your application does not break.
Breaking changes such as removing or renaming an attribute will be released as a new version
of the API. PolyLogyx will provide a migration path for new versions of APIs and will
communicate timelines for end-of-life when deprecating APIs. Do not consume any API unless it
is formally documented. All undocumented endpoints should be considered private, subject to
change without notice, and not covered by any agreements.

The API version is currently v0.

All API requests must use the https scheme.

## Base URL
API calls are made to a URL to identify the location from which the data is accessed. You must replace
the placeholders <server IP> and 5000 port with actual details for your PolyLogyx server. The Base URL
follows this template: https://<server_ip>:5000/services/api/v0/

## Error Codes

| Code | Description |
|------------|--------------|
|400 |Malformed or bad JSON Request|
|401 |API access without authentication or invalid API key|
|404 |Resource not found|
|422 |Request can be parsed. But, has invalid content|
|429 |Too many requests. Server has encountered rate limits|
|200 |Success|
|201 |Created. Returns after a successful POST when a resource is created|
|500 |Internal Server Error|
|503 |Service Currently Unavailable|

### 4.1.2 Get Node by host identifier

URL: https://<Base URL>/nodes/<host_identifier>
 
Request Type: GET
Response: A node with its properties.  
 
Example Response
``` json
{
	"data": {
		"enrolled_on": "2018-07-24 06:22:48",
		"host_identifier": "77858CB1-6C24-584F-A28A-E054093C8924",
		"last_checkin": "2018-08-01 13:42:05",
		"network_info": {
			"mac_address": "54:26:96:d7:9a:65"
		},
		"node_info": {
			"computer_name": "",
			"cpu_physical_cores": "2",
			"hardware_model": "MacBookPro10,2",
			"hardware_serial": "C02KV7RJDR53",
			"hardware_vendor": "Apple Inc.",
			"physical_memory": "8589934592"
		},
		"node_key": "10b18bd8-9e5e-455f-bd48-8d7c456b841f",
		"tags": [
			"second",
			"thirdsssss",
			"first"
		]
	},
	"message": "Successfully fetched the node info",
	"status": "success"
} 


