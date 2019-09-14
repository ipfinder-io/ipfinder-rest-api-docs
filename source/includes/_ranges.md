# IP Address Ranges
Our IP address ranges API will return a list of all of the IP addresses ranges assigned to or operated by a company, identified by the Organization name. So, you provide a Organization name, and we return all of the IP address ranges in CIDR format that belong to that company.

This API is currently only available as part of our enterprise 

## Examples Ranges

Here are sample command lines for fetching API service information :

### HTTP Request

`GET https://api.ipfinder.io/v1/ranges/$ORGNAME?token=$token`

`POST https://api.ipfinder.io/v1/ranges/$ORGNAME`

### The parameters are defined as follows :
```shell
# With POST
curl -X POST -d '{"token":"$TOKEN"}' -H "Content-Type: application/json" http://api.ipfinder.io/v1/ranges/$ORGNAME

# With token query parameter

CURL -X GET 'http://api.ipfinder.io/v1/ranges/Telecom%20Algeria?token=$TOKEN'

```
```php
<?php 
use ipfinder\ipfinder\IPfinder;

// Token
$client = new IPfinder('YOUR_TOKEN_GOES_HERE'); 

// Organization name
$org = 'Telecom Algeria';

// lookup Organization information
$details = $client->getRanges($org);

var_dump($client);

// print Organization name url encode  
echo $client->urlencode;
```

```python
import ipfinder

config = ipfinder.config('YOUR_TOKEN_GOES_HERE')

# Organization name
org = 'Telecom Algeria'

# lookup Organization information
data = config.getRanges(org)

data.details
```

```javascript
const Ipfinder = require('ipfinder');
const ipfinder = new Ipfinder('YOUR_TOKEN_GOES_HERE');

ipfinder.getRanges("Telecom Algeria").then(data => {
     console.log(data);
    // console.log(data.status_message);
}).catch(console.log);
```

```ruby
require 'ipfinder'
config = Ipfinder::config('YOUR_TOKEN_GOES_HERE')

# Organization name
org = 'Telecom Algeria'

# lookup Organization information
range = config.getRanges(org)

puts range.inspect
```

```java
        Ipfinder ipfinder = new Ipfinder("YOUR_TOKEN_GOES_HERE", "");

        try {

            String org = "Telecom Algeria";
            
            RangeResponse response = ipfinder.getRanges(org);

            // print data
            System.out.println(response);

        } catch (IPfinderException ex) {
            // Handle error
            System.out.println(e);
        }
```

```lua
local inspect = require('inspect')
local ipfinder = require('ipfinder')

conf = Ipfinder:init("YOUR_TOKEN_GOES_HERE")

-- lookup Organization information
range = conf:getRanges("Telecom Algeria")

print(inspect(range))
```

```d
        Ipfinder ipfinder = new Ipfinder("YOUR_TOKEN_GOES_HERE");

        try {

            string org = "Telecom Algeria";

            JSONValue response = ipfinder.getRanges(org);

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

# lookup Organization information
range <- getRanges(conf,"Telecom Algeria")

range
```

```elixir
iex> conf = Ipfinder.new("YOUR_TOKEN_GOES_HERE")

# lookup Organization information
iex> {:ok, range} = Ipfinder.getRanges(conf,"Telecom Algeria")

iex> range
```

```swift
import ipfinder
let ipfinder = Ipfinder("YOUR_TOKEN_GOES_HERE")

// lookup Organization information
let range = ipfinder.getRanges("Telecom Algeria")

print(range)
```

```go 
// lookup Organization information
func main() {
  conf := ipfinder.New("YOUR_TOKEN_GOES_HERE", "")
  ranges, err := conf.GetRanges("Telecom Algeria")

  if err != nil {
    fmt.Println("Error : ", err)
  } else {
    fmt.Println(ranges)
  }
}
```


```powershell

  # shortopt
$ ipfinder -r  'Telecom Algeria'
  # longopt
$ ipfinder --ranges  'Telecom Algeria'

```


> Make sure to convert $ORGNAME  into URL encoding 

Parameter | Default  | Description
--------- | -------  | -----------
`token`   | Required | Your API key 
`ORGNAME` | Required | Organization name convert into URL encoding [URL encoding](https://rosettacode.org/wiki/URL_encoding)


## Response Objects details

```json
{
    "status": "ok",
    "status_message": "Query was successful",
    "org_name": "University of Indianapolis",
    "continent_code": "NA",
    "continent_name": "North America",
    "country_name": "United States",
    "domain": "unive.nl",
    "num_ranges": "724",
    "num_ipv4": "13,120,004",
    "num_ipv6": "11,648,129,627,049,650,863,615,699,320,832",
    "num_asn": 89,
    "list_asn": [
        {
            "asn": "396892",
            "OrgId": "UNIVER-246",
            "Total_prefix": "4",
            "Total_v4": "2,560",
            "Total_v6": "0"
        },
        {
            "asn": "394003",
            "OrgId": "UMD",
            "Total_prefix": "1",
            "Total_v4": "65,536",
            "Total_v6": "0"
        },
        {
            "asn": "328215",
            "OrgId": "ORG-UCS1-AFRINIC",
            "Total_prefix": "1",
            "Total_v4": "256",
            "Total_v6": "0"
        }
        ....
        ....
        ....
        ....
    ],
    "list_prefixes": [

        {
            "asn": "2",
            "prefix": "103.219.213.0\/24"
        },
        {
            "asn": "2",
            "prefix": "128.4.0.0\/16"
        },
        {
            "asn": "2",
            "prefix": "168.194.156.0\/23"
        },
        {
            "asn": "2",
            "prefix": "168.194.158.0\/23"
        },
        {
            "asn": "2",
            "prefix": "168.195.232.0\/24"
        },
        {
            "asn": "2",
            "prefix": "168.195.233.0\/24"
        }
        ....
        ....
        ....
        ....
    ]
}

```

Response Object   | Description
---------         |  -----------
`domain`          |  Returns provided domain name
`num_ranges`      |  Returns total number of CIDR
`num_ipv4`        |  Returns Total number of IPV4
`num_ipv6`        |  Returns total number of IPV6
`num_asn`         |  Returns total number of AS number
`ranges`          | [Object] Returns an object containing CIDR-related data.
