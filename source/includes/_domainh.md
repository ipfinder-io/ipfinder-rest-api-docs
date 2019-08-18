## Get list Domain By ASN, Country,Ranges

Here are sample command lines for fetching API service information :

```shell
# Get list domain by as11
curl -XGET https://api.ipfinder.io/v1/domainby/AS11?token=$TOKEN

# Get list domain by country  DZ
curl -XGET https://api.ipfinder.io/v1/domainby/DZ?token=$TOKEN

# Get list domain by organization name
curl -XGET https://api.ipfinder.io/v1/domainby/Google%20LLC?token=$TOKEN


```



### HTTP Request

`GET https://api.ipfinder.io/v1/domainby/{$select_by}?token=$TOKEN&format=$format`

`POST https://api.ipfinder.io/v1/domainby/{$select_by}`

### The parameters are defined as follows :



Parameter | Default | Description
--------- | ------- | -----------
token     | Required | Your API key 
$select_by | Required | The API supports passing in a single website name domain name
format    | optional | available format `json` `jsonp` `php` `xml`

## Domain By ASN  Objects details

```json
{
    "status": "ok",
    "status_message": "Query was successful",
    "select_by": "country US",
    "total_domain": ???,
    "list_domain": [
        [
            {
                "domain_name": "google.com",
                "address": "172.217.17.46",
                "country": "US",
                "asn": "15169",
                "organization": "Google LLC"
            },
            {
                "domain_name": "sa3i9a.com",
                "address": "104.24.97.206",
                "country": "US",
                "asn": "13335",
                "organization": "  NOC"
            },
            {
                "domain_name": "stackoverflow.com",
                "address": "151.101.1.69",
                "country": "US",
                "asn": "54113",
                "organization": "Fastly"
            },
            {
                "domain_name": "stackoverflow.com",
                "address": "151.101.193.69",
                "country": "US",
                "asn": "54113",
                "organization": "Fastly"
            },
            {
                "domain_name": "google.com",
                "address": "172.217.17.110",
                "country": "US",
                "asn": "15169",
                "organization": "Google LLC"
            }
            ....
            ....
            ....
            ....
            ....
            ....
        ]
    ]
}
```

Response Object               | Description
---------                     |  -----------
`select_by`                   |  Returns Requested $select_by `ASN`,`Country`,`Ranges`
`total_domain`                |  Returns number of domain
`list_domain`                 | [Object] Returns an object containing list domain name
`list_domain`->`domain_name`  |  Returns the domain name
`list_domain`->`address`      |  Returns IP address 
`list_domain`->`country`      |  Returns ISO 3166-1 alpha-2 country code
`list_domain`->`asn`          | Returns the Autonomous System Number associated with the IP.
`list_domain`->`organization` | Returns the name of the organization associated with the IP.