# Filtering Responses
You can filter the API response down to specific fields or objects by adding the field or object name to the URL. In the case of a field you'll get it returned in plaintext, and an object will get returned as JSON.
```
# Get json the type field as plaintext
$ curl -XGET 'https://api.ipfinder.io/v1/1.0.0.0?token=free&propertyName=type'
IPV4.

# Get just the city as plaintext
$ curl -XGET 'https://api.ipfinder.io/v1/1.0.0.0?token=free&propertyName=city'
"South Brisbane"
```
