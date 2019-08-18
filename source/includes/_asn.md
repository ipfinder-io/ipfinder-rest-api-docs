# Get AS details

## Examples
Here are sample command lines for fetching API service information :

```shell
# With GET Get details for 1.0.0.0
curl -X GET https://api.ipfinder.io/v1/(asNumber)?token=$TOKEN

# With POST Get details for 1.0.0.0
curl -d '{"token":"$TOKEN"}' /
     -H "Content-Type: application/json" /
      -X POST /
       https://api.ipfinder.io/v1/(asNumber)

# parameters Examples
# jsonp
curl -d '{"token":"$TOKEN", "format":"jsonp", "callback": "test"}' /
     -H "Content-Type: application/json" /
      -X POST /
       https://api.ipfinder.io/v1/(asNumber)


# xml 
curl -d '{"token":"$TOKEN", "format" : "xml"}' /
     -H "Content-Type: application/json" /
     -X POST /
      https://api.ipfinder.io/v1/(asNumber)


# php
curl -d '{"token":"$TOKEN", "format" : "php"}' /
     -H "Content-Type: application/json" /
     -X POST https://api.ipfinder.io/v1/(asNumber)
```


> Make sure to replace Add `(as|AS)` to `asNumber` example `as1` or `AS1`.


### HTTP Request

`GET https://api.ipfinder.io/v1/(as|AS){asNumber}?token=$TOKE`

`POST https://api.ipfinder.io/v1/as`


### The parameters are defined as follows :
Parameter       | Default | Description
---------       | ------- | -----------
`token`         | Required | Your API key or the string "free" for the free API
`asNumber`      | Required | The AS number you want details for
`format`        | optional | available format `json` `jsonp` `php` `xml`
`callback`      | optional | add callback name if format equal `jsonp`
`propertyName`  | optional |  specify a single field name to request instead of the whole address details


## Response object
> Full Response


```json
{
    "status": "ok",
    "status_message": "Query was successful",
    "asn": "AS36947",
    "org_name": "Telecom Algeria",
    "continent_code": "AF",
    "continent_name": "Africa",
    "country_code": "DZ",
    "country_name": "Algeria",
    "allocated": "2007-04-27",
    "registry": "afrinic",
    "domain": "algerietelecom.dz",
    "num_ips_ipv4": "4,353,792",
    "num_ips_ipv6": "79,228,162,514,264,337,593,543,950,336",
    "as_name": "ALGTEL-AS",
    "org_id": "ORG-TA23-AFRINIC",
    "comany_type": "isp",
    "speed": {
        "ping": "270.1 ms",
        "download": "10.97 ms",
        "upload": "0.79 ms"
    },
    "peers": {
        "total_peers": 4,
        "list_peers": [
            "AS12956",
            "AS174",
            "AS5511",
            "AS6762"
        ]
    },
    "upstreams": {
        "total_upstreams": 4,
        "list_upstreams": [
            "AS12956",
            "AS174",
            "AS5511",
            "AS6762"
        ]
    },
    "downstreams": {
        "total_downstreams": 3,
        "list_downstreams": [
            "AS327712",
            "AS327931",
            "AS33779"
        ]
    },
    "prefixes": {
        "total_prefixes": 261,
        "list_prefixes": [
            "41.96.0.0\/16",
            "41.96.0.0\/13",
            
        ]
    }
}
```
Response Object                           | Description
---------                                 | -----------
`asn`                                     | AS number
`org_name`                                | Organization name
`continent_code`                          | 2-letter continent code
`continent_name`                          | Continent name
`country_code`                            |  ISO 3166-1 alpha-2 country code
`country_name`                            |  Country name
`registry`                                | Regional internet registry `afrinic`, `lacnic`, `apnic`, `arin`, `ripe` and more..
`domain`                                  |  Website of Organization
`num_ips_ipv4`                            |  Total number of IPv4 addresses announced by this AS
`num_ips_ipv6`                            |  Total number of IPv6 addresses announced by this AS
`as_name`                                 |  AS name
`org_id`                                  |  Organization ID
`comany_type`                             |  Returns `isp`, `business` , `hosting`, `other` .
`speed`                                   |  [Object] Returns an object containing Network Speed-related data.
`speed`->`ping`                           |  Returns the Network Speed ping of  AS number.
`speed`->`download`                       |  Returns the Network Speed download of  AS number.
`speed`->`upload`                         |  Returns the Network Speed upload of  AS number.
`peers`                                   |  [Object] Returns an object containing peers-related data.
`peers`->`total_upstreams`                |  Returns the Total number of peers announced by this AS number
`peers`->`list_upstreams`                 |  Returns the list of `AS` announced by this AS number (e.g. `AS1`)
`upstreams`                               |  [Object] Returns an object containing upstreams-related data.
`upstreams`->`total_upstreams`            |  Returns the Total number of upstreams announced by this AS number
`upstreams`->`list_upstreams`             |  Returns the list of `AS` announced by this AS number (e.g. `AS1`)
`downstreams`                             |  [Object] Returns an object containing downstreams-related data.
`downstreams`->`total_downstreams`        |  Returns the Total number of downstreams announced by this AS number
`downstreams`->`list_downstreams`         |  Returns the list of `AS` announced by this AS number (e.g. `AS1`)
`prefixes`                                |  [Object] Returns an object containing prefixes-related data.
`prefixes`->`total_prefixes`              |  Returns the Total number of prefixes announced by this AS
`prefixes`->`list_prefixes`               |  Returns the list of prefixes `CIDR` announced by this AS (e.g. `41.96.0.0\/16`)
