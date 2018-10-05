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

