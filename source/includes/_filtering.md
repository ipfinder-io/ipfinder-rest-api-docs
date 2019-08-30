# Filtering Responses
You can filter the API response down to specific fields or objects by adding the field or object name to the URL. In the case of a field you'll get it returned in plaintext, and an object will get returned as JSON.
```
# Get json the type field as plaintext
curl -X GET https://api.ipfinder.io/v1/1.0.0.0?token=free
{
    "status": "ok",
    "status_message": "Query was successful",
    "ip": "1.0.0.0",
    "type": "IPV4",
    "continent_code": "OC",
    "continent_name": "Oceania",
    "country_code": "AU",
    "country_name": "Australia",
    "country_native_name": "Australia",
    "region_name": "Queensland",
    "city": "South Brisbane"

```
