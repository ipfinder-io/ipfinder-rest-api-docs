# Get IP address details

In order to fetch information about an IP address, you need to build a request URL of the following form :


## Examples



```shell
# With GET Get details for 1.0.0.0
curl -X GET https://api.ipfinder.io/v1/1.0.0.0?token=$TOKEN

# With POST Get details for 1.0.0.0
curl -d '{"token":"$TOKEN"}' /
     -X POST /
      https://api.ipfinder.io/v1/1.0.0.0

# With X-Authorization token details for 1.0.0.0
curl  -H 'X-Authorization:$TOKEN' /
      -X GET /
       https://api.ipfinder.io/v1/1.0.0.0

# parameters Examples
# jsonp
curl -d '{"token":"$TOKEN", "format":"jsonp", "callback": "test"}' /
     -H "Content-Type: application/json" /
     -X POST  /
     https://api.ipfinder.io/v1/1.0.0.0


# xml 
curl -d '{"token":"$TOKEN", "format" : "xml"}' /
     -H "Content-Type: application/json" /
     -X POST /
      https://api.ipfinder.io/v1/169.57.0.140


# php
curl -d '{"token":"$TOKEN", "format" : "php"}' /
     -H "Content-Type: application/json" /
     -X POST /
      https://api.ipfinder.io/v1/169.57.0.140

```

```php
<?php 

use ipfinder\ipfinder\IPfinder;

// Token
$client = new IPfinder('YOUR_TOKEN_GOES_HERE'); 

// GET Get details for 1.0.0.0
$ip_address = '1.0.0.0'; 

// lookup IP address information

$details = $client->getAddressInfo($ip_address);

var_dump($details);
```

```python
import ipfinder

config = ipfinder.config('YOUR_TOKEN_GOES_HERE')

# GET Get details for 1.0.0.0

ip = config.getAddressInfo('1.0.0.0')

ip.details
```

```javascript
const Ipfinder = require("ipfinder");
const ipfinder = new Ipfinder();

ipfinder.getAddressInfo("1.0.0.0").then(data => {
     console.log(data);
    // console.log(data.status_message);
}).catch(console.log);
```

```ruby
require 'ipfinder'
config = Ipfinder::config('YOUR_TOKEN_GOES_HERE')

# GET Get details for 1.0.0.0
ip_address = '1.0.0.0'

# lookup IP address information
ip = config.getAddressInfo('1.0.0.0')

puts ip.inspect
```
```java
        Ipfinder ipfinder = new Ipfinder("YOUR_TOKEN_GOES_HERE", ""); 

        try {

            // lookup your IP address information
            String ip = "5.2.0.2";
            
            IPResponse response = ipfinder.getAddressInfo(ip);

            System.out.println(response.toString());

            // print city name
            System.out.println(response.getCity());

        } catch (IPfinderException e) {
            // Handle error
        }
```

```lua
local inspect = require('inspect')
local ipfinder = require('ipfinder')

conf = Ipfinder:init("YOUR_TOKEN_GOES_HERE")

-- GET Get details for 1.0.0.0
ip = conf:getAddressInfo("1.0.0.0")

print(inspect(ip))

print(ip.ip)
```

```powershell

  # shortopt
$ ipfinder -i 5.5.5.5
  # longopt
$ ipfinder --ip 2.2.2.2

```

Here are a few examples for fetching IP address information from the command line :



### HTTP Request

`GET https://api.ipfinder.io/v1/{ipAddress}?token=$TOKEN`

`POST https://api.ipfinder.io/v1/{ipAddress}`

### The parameters are defined as follows :


Parameter | Default | Description
--------- | ------- | -----------
token     | Required | Your API key or the string "free" for the free API
ipAddress | Required | The API supports passing in a single IPv4 or IPv6 IP address 
format    | optional | available format `json` `jsonp` `php` `xml`
callback  | optional | add callback name if format equal `jsonp`
propertyName  | optional |  specify a single field name to request instead of the whole address details




## Response  Objects details
Depending on your subscription plan and the options you choose for your API request, the ipstack API will respond using a series of different modules and objects. Find below a list of all available API response objects explained.
> Full Response


```json
{
    "status": "ok",
    "status_message": "Query was successful",
    "ip": "169.57.0.140",
    "type": "IPV4",
    "continent_code": "NA",
    "continent_name": "North America",
    "country_code": "US",
    "country_name": "United States",
    "country_native_name": "United States",
    "region_name": "Minnesota",
    "city": "Rochester",
    "latitude": "44.0592",
    "longitude": "-92.5063",
    "location": {
        "capital": "Washington, D.C.",
        "country_flag": "http:\/\/fipfinder.io\/flag\/usa.svg",
        "flag_png": "http:\/\/fipfinder.io\/flag\/usa.png",
        "country_flag_emoji": "\ud83c\uddfa\ud83c\uddf8",
        "country_flag_emoji_unicode": "U+1F1FA U+1F1F8",
        "calling_code": "1",
        "toplevel_domain": ".us",
        "alpha3_code": "USA",
        "population": "321645000",
        "is_eu": false,
        "is_ar": false
    },
    "time_zone": {
        "id": "America\/New_York",
        "UTC": "UTC\u221212:00",
        "gmt_offset": -18000,
        "current_time": "2019-02-18 14:08:18"
    },
    "currency": {
        "name": "United States dollar",
        "symbol": "USD",
        "symbol_native": "$"
    },
    "languages": {
        "code": "en",
        "name": "English",
        "name_native": "English"
    },
    "connection": {
        "asn": "36351",
        "organization": "SoftLayer Technologies Inc.",
        "domain": "softlayer.com",
        "type": "Hosting"
    },
    "security": {
        "is_proxy": false,
        "proxy_type": false,
        "is_tor": false,
        "is_spam": false,
        "threat_level": "Low"
    },
    "header": {
        "total_user_agent": 8,
        "list_user_agent": [
            {
                "user_agent": "Mozilla\/5.0 (Windows NT 6.1) AppleWebKit\/537.36 (KHTML, like Gecko) Chrome\/41.0.2228.0 Safari\/537.36",
                "browser_name": "Chrome",
                "os_name": "Windows",
                "device_type": "desktop"
            },
            {
                "user_agent": "Mozilla\/5.0 (Linux; U; Android 4.0.4; en-us; Glass 1 Build\/IMM76L; XE10) AppleWebKit\/534.30 (KHTML, like Gecko) Version\/4.0 Mobile Safari\/534.30",
                "browser_name": null,
                "os_name": null,
                "device_type": "headset"
            },
            {
                "user_agent": "Mozilla\/5.0 (compatible; IBrowse 3.0; AmigaOS4.0)\r\n",
                "browser_name": "IBrowse",
                "os_name": "AmigaOS",
                "device_type": "desktop"
            },
            {
                "user_agent": "Mozilla\/5.0 (Linux; U; Android 2.1-update1; en-au; HTC_Desire_A8183 V1.16.841.1 Build\/ERE27) AppleWebKit\/530.17 (KHTML, like Gecko) Version\/4.0 Mobile Safari\/530.17",
                "browser_name": "Android Browser",
                "os_name": "Android",
                "device_type": "mobile"
            },
            {
                "user_agent": "Feed Viewer 3.9.3843.18128",
                "browser_name": null,
                "os_name": null,
                "device_type": ""
            },
            {
                "user_agent": "itunes\/9.0.2 (Macintosh; Intel Mac OS X 10.4.11) AppleWebKit\/531.21.8",
                "browser_name": null,
                "os_name": "OS X",
                "device_type": "desktop"
            },
            {
                "user_agent": "Mozilla\/5.0 (compatible; Googlebot\/2.1; +http:\/\/www.google.com\/bot.html)",
                "browser_name": "Googlebot",
                "os_name": null,
                "device_type": "bot"
            },
            {
                "user_agent": "Mozilla\/5.0 (X11; Linux x86_64) AppleWebKit\/535.2 (KHTML, like Gecko) Ubuntu\/11.04 Chromium\/15.0.871.0 Chrome\/15.0.871.0 Safari\/535.2",
                "browser_name": "Chromium",
                "os_name": "Ubuntu",
                "device_type": "desktop"
            }
        ]
    }
}
```
Response Object    | Description
--------- | -----------
`ip`                                      | Requested IP address
`type`                                    | IP address 
`continent_code`                          | 2-letter continent code
`continent_name`                          | Continent name
`country_code`                            |  ISO 3166-1 alpha-2 country code
`country_name`                            |  Country name
`country_native_name`                     |  Country native name
`region_name`                             |  State or province name
`city`                                    |  City name
`latitude`                                |  Decimal latitude
`longitude`                               |  Decimal longitude
`location`                                |  [Object] List of location  raised by IP address 
`location`->`capital`                     |  Returns the capital city of the country associated with the IP.
`location`->`country_flag`                |  Returns an HTTP URL leading to an SVG-flag icon for the country associated with the IP.
`location`->`flag_png`                    |  Returns an HTTP URL leading to an PNG-flag icon for the country associated with the IP.
`location`->`country_flag_emoji`          |  Returns the emoji icon for the flag of the country associated with the IP.
`location`->`country_flag_emoji_unicode`  |  Returns the unicode value of the emoji icon for the flag of the country associated with the IP. (e.g. `U+1F1F5 U+1F1F9` for the Portuguese flag)
`location`->`calling_code`                |  Returns the calling/dial code of the country associated with the IP. (e.g. `351`) for Portugal.
`location`->`toplevel_domain`             |  Returns country domain name (e.g `.dz` `.co` )
`location`->`alpha3_code`                 |  ISO 3166-1 alpha-3 country code
`location`->`population`                  |  Country population
`location`->`is_eu`                       |  Returns `true` or `false` depending on whether or not the county associated with the IP is in the European Union.
`location`->`is_ar`                       |  Returns `true` or `false` depending on whether or not the county associated with the IP is in the ARABIC Union.
`time_zone`                               |  [Object] Returns an object containing timezone-related data.
`time_zone`->`id`                         |  Returns the ID of the time zone associated with the IP. (e.g. `Australia/Lord_Howe` for PST)
`time_zone`->`UTC`                        |  UTC 
`time_zone`->`gmt_offset`                 |  Returns the GMT offset of the given time zone in seconds. (e.g. `-25200` for PST's -7h GMT offset)
`time_zone`->`current_time`               |  Returns the current date and time in the location associated with the IP. (e.g. `2019-02-19 06:58:25`)
`currency`                                |  [Object] Returns an object containing currency-related data.
`currency`->`name`                        |  Returns the name of the given currency.
`currency`->`symbol`                      |  Returns the 3-letter code of the main currency associated with the IP.Example: `USD`
`currency`->`symbol_native`               |  Returns the native symbol letter of the given currency .Example: `$`.
`languages`                               |  [Object] Returns an object containing one or multiple sub-objects per language spoken in the country associated with the IP.
`languages`->`code`                       |  Returns the 2-letter language code for the given language. 
`languages`->`name`                       |  Returns the name (in the API request's main language) of the given language. (e.g. `Arabic`)
`languages`->`name_native`                |  Returns the native name of the given language. (e.g. `العربية`)
`connection`                              |  [Object] Returns an object containing connection-related data.
`connection`->`asn`                       |  Returns the Autonomous System Number associated with the IP.
`connection`->`organization`              |  Returns the name of the organization associated with the IP.
`connection`->`domain`                    |  Returns the name of the domain associated with the IP.
`connection`->`type`                      |  Returns the name of the type associated with the IP  List of all available (`isp`, `hosting`, `Business`, `Other`).
`security`                                |  [Object] Returns an object containing security-related data.
`security`->`is_proxy`                    |  Returns `true` or `false` depending on whether or not the given IP is associated with a proxy.
`security`->`proxy_type`                  |  Returns the type of proxy the IP is associated with. List of all available(`cgi`, `web`, `vpn`)
`security`->`is_tor`                      |  Returns `true` or `false` depending on whether or not the given IP is associated with the anonymous Tor system.
`security`->`is_spam`                     |  Returns `true` or `false` depending on whether or not the given IP is associated with the spammer db .
`security`->`threat_level`                |  Returns the type of threat level the IP is associated with. List of all available(`low`, `medium`, `high`)
`header`                                  |  [Object] Returns an object containing header-related data.
`header`->`total_user_agent`              |  Returns an number of User Agent associated with the IP.
`header`->`list_user_agent`               |  [Object] Returns an object containing  User Agent-related data(`user_agent`,`browser_name`,`os_name`,`device_type`).
