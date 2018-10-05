# Chapter 1

## REST Based API

* Makes use of standard HTTP verbs

| Code | Description |
|------------|--------------|
|400 |Malformed or bad JSON Request|
|401 |API access without authentication or invalid API key|
|404 |Resource not found|
|422 |Request can be parsed. But, has invalid content|
|429 |Too many requests. Server has encountered rate limits|
|200 |Success|
|201 |Created. Returns after a successful POST when a resource is created|

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


