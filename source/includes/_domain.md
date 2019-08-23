#  Domain 

This API is currently only available as part of our enterprise

## Get Domain IP

Here are sample command lines for fetching :

```shell
# With token query parameter

curl -XGET https://api.ipfinder.io/v1/domain/google.com?token=$TOKEN

```
```php
<?php 
use ipfinder\ipfinder\IPfinder;

// Token
$client = new IPfinder('YOUR_TOKEN_GOES_HERE'); 

// domain name
$name = 'google.com';

// lookup Organization information
$details = $client->getDomain($name);

var_dump($details);
```

```python
import ipfinder

config = ipfinder.config('YOUR_TOKEN_GOES_HERE')

#  domain name
name = 'google.com';

data = config.getDomain(name)

data.details
```

```javascript
const Ipfinder = require('ipfinder');
const ipfinder = new Ipfinder('YOUR_TOKEN_GOES_HERE');

ipfinder.getDomain("google.com").then(data => {
     console.log(data);
    // console.log(data.status_message);
}).catch(console.log);
```

```ruby
require 'ipfinder'
config = Ipfinder::config('YOUR_TOKEN_GOES_HERE')

# lookup domain name data
name = 'google.com'

domain = config.getDomain(name)

puts domain.inspect
```

### HTTP Request

`GET https://api.ipfinder.io/v1/domain/$DomainName?token=$TOKEN&format=$Format`

`POST https://api.ipfinder.io/v1/domain/$DomainName`

### The parameters are defined as follows :



Parameter | Default | Description
--------- | ------- | -----------
token     | Required | Your API key
$DomainName | Required | The API supports passing in a single website name domain name
format    | optional | available format `json` `jsonp` `php` `xml`



## Domain IP  Objects details

```json
{
    "status": "ok",
    "status_message": "Query was successful",
    "ip": "172.217.171.238",
    "domain": "google.com",
    "domain_status": true,
    "continent_code": "AS",
    "continent_name": "Asia",
    "country_code": "SG",
    "country_name": "Singapore",
    "country_native_name": "Singapore",
    "region_name": "Central Singapore",
    "city": "Singapore",
    "latitude": "1.28009",
    "longitude": "103.851",
    "asn": "AS15169",
    "organization": "Google LLC"
}
```

Response Object   | Description
---------         |  -----------
`ip`                   | IP address  
`domain`               | Requested domain
`domain_status`        | If domain is live Return `true` else `false`  domain is down
`continent_code`       | 2-letter continent code
`continent_name`       | Continent name
`country_code`         | ISO 3166-1 alpha-2 country code
`country_native_name`  | Country native name
`region_name`          | State or province name
`city`                 | City name
`latitude`             | Decimal latitude
`longitude`            | Decimal longitude
`asn`                  | the Autonomous System Number associated with the IP
`organization`         | the name of the organization associated with the IP
