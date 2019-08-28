## Get Domain IP history

Here are sample command lines for fetching API service information :

```shell
# With token query parameter

curl -XGET https://api.ipfinder.io/v1/domainhistory/google.com?token=$TOKEN

```


```php
<?php 
use ipfinder\ipfinder\IPfinder;

// Token
$client = new IPfinder('YOUR_TOKEN_GOES_HERE'); 

// domain name
$name = 'google.com';

// lookup Organization information
$details = $client->getDomainHistory($name);

var_dump($details);
```
```python
import ipfinder

config = ipfinder.config('YOUR_TOKEN_GOES_HERE')

# domain name
name = 'google.com';

data = config.getDomainHistory(name)

data.details
```
```javascript
const Ipfinder = require('ipfinder');
const ipfinder = new Ipfinder('YOUR_TOKEN_GOES_HERE');

ipfinder.getDomainHistory("google.com").then(data => {
     console.log(data);
    // console.log(data.status_message);
}).catch(console.log);
```

```ruby
require 'ipfinder'
config = Ipfinder::config('YOUR_TOKEN_GOES_HERE')

# lookup domain name IP history
name = 'google.com'

data = config.getDomainHistory(name)

puts data.inspect
```

```java
        Ipfinder ipfinder = new Ipfinder("YOUR_TOKEN_GOES_HERE", "");

        try {
            String by = "DZ";

            DomainByResponse response = ipfinder.getDomainBy(by);

            // print data
            System.out.println(response);

        } catch (IPfinderException ex) {
            // Handle error
            System.out.println(e);
        }
    }
```

```lua
local inspect = require('inspect')
local ipfinder = require('ipfinder')

conf = Ipfinder:init("YOUR_TOKEN_GOES_HERE")
-- domain name IP history
domain = conf:getDomainHistory("google.fr")

print(inspect(domain))
```

```d
        Ipfinder ipfinder = new Ipfinder("YOUR_TOKEN_GOES_HERE");

        try {

            string name = "google.com";

            JSONValue response = ipfinder.getDomainHistory(name);

            // print data
            writeln(response);

        } catch (Exception ex) {
            // Handle error
            writeln(e);
        }
```

```r
require(ipfinder)

conf <- Ipfinder(token="YOUR_TOKEN_GOES_HERE")
# domain name IP history
domain <- getDomainHistory(conf,"google.fr")

domain
```

```powershell

  # shortopt
$ ipfinder -dh google.com
  # longopt
$ ipfinder --dhistory google.com

```

### HTTP Request

`GET https://api.ipfinder.io/v1/domainhistory/$DomainName?token=$TOKEN&format=$Format`

`POST https://api.ipfinder.io/v1/domainhistory/$DomainName`

### The parameters are defined as follows :



Parameter | Default | Description
--------- | ------- | -----------
token     | Required | Your API key 
$DomainName | Required | The API supports passing in a single website name domain name
format    | optional | available format `json` `jsonp` `php` `xml`

## Domain IP history  Objects details

```json
{
    "status": "ok",
    "status_message": "Query was successful",
    "total_domain": 5,
    "list_domain": [
        [
            {
                "domain_name": "google.com",
                "address": "172.217.171.238",
                "country": "SG",
                "asn": "15169",
                "organization": "Google LLC",
                "last_seen_on": "2019-06-16 13:47:09"
            },
            {
                "domain_name": "google.com",
                "address": "216.58.198.78",
                "country": "IT",
                "asn": "15169",
                "organization": "Google LLC",
                "last_seen_on": "2019-06-16 13:43:30"
            },
            {
                "domain_name": "google.com",
                "address": "172.217.168.206",
                "country": "SG",
                "asn": "15169",
                "organization": "Google LLC",
                "last_seen_on": "2019-06-15 18:29:24"
            },
            {
                "domain_name": "google.com",
                "address": "172.217.17.110",
                "country": "US",
                "asn": "15169",
                "organization": "Google LLC",
                "last_seen_on": "2019-06-15 18:29:20"
            },
            {
                "domain_name": "google.com",
                "address": "172.217.17.46",
                "country": "US",
                "asn": "15169",
                "organization": "Google LLC",
                "last_seen_on": "2019-06-07 10:02:15"
            }
        ]
    ]
}
```

Response Object               | Description
---------                     |  -----------
`total_domain`                |  Returns the
`list_domain`                 | [Object] Returns an object containing list domain name
`list_domain`->`domain_name`  |  Returns the domain name
`list_domain`->`address`      |  Returns IP address 
`list_domain`->`country`      |  Returns ISO 3166-1 alpha-2 country code
`list_domain`->`asn`          |  Returns the Autonomous System Number associated with the IP.
`list_domain`->`last_seen_on` |  Returns the last seen date
