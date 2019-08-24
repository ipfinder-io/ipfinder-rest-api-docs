# Get service status

## Examples
Here are sample command lines for fetching API service information :

### HTTP Request

`GET https://api.ipfinder.io/v1/info`

`POST https://api.ipfinder.io/v1/info`

### The parameters are defined as follows :
```shell
# With token query parameter

$ curl -X GET https://api.ipfinder.io/v1/info?token=$TOKEN 

# With Basic Auth
$ curl -u $TOKEN:  https://api.ipfinder.io/v1/info

# With X-Authorization token
$ curl -H 'X-Authorization: $TOKEN' https://api.ipfinder.io/v1/info
```
```php
<?php 
use ipfinder\ipfinder\IPfinder;

// Token
$client = new IPfinder('YOUR_TOKEN_GOES_HERE'); 


// lookup token information

$details = $client->getStatus();

var_dump($details);

// get and print Number of IP address queries left for the day
echo $details->queriesLeft."\n"; 
```

```python
import ipfinder

config = ipfinder.config('YOUR_TOKEN_GOES_HERE')

# lookup TOKEN information
data = config.getStatus()


data.details
```
```javascript
const Ipfinder = require('ipfinder');
const ipfinder = new Ipfinder('YOUR_TOKEN_GOES_HERE');

ipfinder.getStatus().then(data => {
     console.log(data);
    // console.log(data.status_message);
}).catch(console.log);
```

```ruby
require 'ipfinder'
config = Ipfinder::config('YOUR_TOKEN_GOES_HERE')

# lookup IP TOKEN information
data = config.getStatus()

puts data.inspect
```

```powershell

  # shortopt
$ ipfinder -s 
  # longopt
$ ipfinder --status 

```

Parameter | Default | Description
--------- | ------- | -----------
`token`     | Required | Your API key or the string "free" for the free API




## Response Objects details

> Full Response


```json
{
    "apiKey": "$TOKEN",
    "queriesPerDay": 50000,
    "queriesLeft": 49993,
    "asqueriesPerDay": 1000,
    "asqueriesLeft": 976,
    "key_type": "E50",
    "key_info": "Enterprise API 50.000 queries per day",
    "status": "active"
}

```

Response Object   | Description
---------         |  -----------
`apiKey`          |  Your API key
`queriesPerDay`   |  Quota of daily IP address queries
`queriesLeft`     |  Number of IP address queries left for the day
`asqueriesPerDay` |  Quota of daily AS number queries only for `Pro` and `Enterprise` KEY
`asqueriesLeft`   |  Number of AS number queries left for the day only for `Pro` and `Enterprise` KEY
`key_type`        |  API key info
`key_info`        |  API key description
`status`          |  The status of your API service `active` `canceled`
