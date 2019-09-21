# Firewall
Do you want to block visitors by country or  AS number ?

This API is currently only available as part of our enterprise


<aside class="notice">
<code>Important</code>  Please update this list every month
</aside>

## Examples Firewall

Here are sample command lines for fetching API service information :

### HTTP Request

`GET https://api.ipfinder.io/v1/firewall/{by}?token=$TOKEN&format=$Format`

`POST https://api.ipfinder.io/v1/firewall/{by}`

```shell
# X-Authorization
 curl -H 'X-Authorization:  $TOKEN' -d "format=microtik"  -X POST http://api.ipfinder.io/v1/firewall/as2

# POST
 curl -d '{"token":"$TOKEN", "format": "microtik"}' -H "Content-Type: application/json" -X POST http://api.ipfinder.io/v1/firewall/as2

# GET 
 curl -X GET 'http://api.ipfinder.io/v1/firewall/as2?token=$TOKEN&format=apache_allow'
```

```php
<?php
use ipfinder\ipfinder\IPfinder;
// Token
$client = new IPfinder('YOUR_TOKEN_GOES_HERE'); // YOUR_TOKEN_GOES_HERE
$asn = 'as1'; // as36947

// lookup Asn information or change to country code us , de, fr
$details = $client->getFirewall($asn,'nginx_deny');
var_dump($details);
```

```python
import ipfinder

config = ipfinder.config('YOUR_TOKEN_GOES_HERE')

asn = 'as36947'

# lookup Firewall information

data = config.getFirewall(asn, 'nginx_deny')

data.details
```

```javascript
const Ipfinder = require('ipfinder');
const ipfinder = new Ipfinder('YOUR_TOKEN_GOES_HERE');

ipfinder.getFirewall("AS1", 'nginx_deny').then(data => {
     console.log(data);
    // console.log(data.status_message);
}).catch(console.log);
```

```ruby
require 'ipfinder'
config = Ipfinder::config('YOUR_TOKEN_GOES_HERE')

asn = 'as36947'
format = 'nginx_deny'
# lookup Asn Firewall information

firewall = config.getFirewall(asn, format)

puts firewall.inspect
```

```java
        Ipfinder ipfinder = new Ipfinder("YOUR_TOKEN_GOES_HERE", "");

        try {

            String asn = "as36947";

            String format = "nginx_deny";

            String response = ipfinder.getFirewall(asn,format);

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

-- lookup Asn Firewall information
fire = conf:getFirewall("AS1", 'nginx_deny')

print(inspect(fire))
```

```d
        Ipfinder ipfinder = new Ipfinder("YOUR_TOKEN_GOES_HERE");

        try {

            string asn = "as36947";

            string format = "nginx_deny";

            string response = ipfinder.getFirewall(asn,format);

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

# lookup Asn Firewall information
fire <- getFirewall(conf,"AS1", 'nginx_deny')

fire
```

```elixir
iex> conf = Ipfinder.new("YOUR_TOKEN_GOES_HERE")

# lookup Asn Firewall information
iex> {:ok, fire} = Ipfinder.getFirewall(conf,"AS1", 'nginx_deny')

iex>fire
```

```swift
import ipfinder
let ipfinder = Ipfinder("YOUR_TOKEN_GOES_HERE")

// lookup Asn Firewall information
let fire = ipfinder.getFirewall("AS1", format:"nginx_deny")

print(fire)
```

```go 
// lookup Asn Firewall information
func main() {
  conf := ipfinder.New("YOUR_TOKEN_GOES_HERE", "") 
  fire, err := conf.GetFirewall("as1", "nginx_deny")

  if err != nil {
    fmt.Println("Error : ", err)
  } else {
    fmt.Println(fire)
  }
}
```

```dart
import 'package:ipfinder/ipfinder.dart';

void main() async {
  Ipfinder ipfinder = Ipfinder("YOUR_TOKEN_GOES_HERE");
  Response fire = await ipfinder.getFirewall("AS1", "nginx_deny");
  print(fire); // print json data
}
```


```powershell

  # shortopt
$ ipfinder -f AS1 --m juniper_junos
  # longopt
$ ipfinder --firewall AS1 --format juniper_junos

```

>  replace `$Format` with available Format name.

Parameter | Default | Description
--------- | ------- | -----------
`token`   | Required | Your API key only for `Enterprise` key
`by`      | Required | AS number `as` (e.g. `AS1`) or `country` ISO 3166-1 alpha-2 country code (e.g. `US`)
`Format`  | Required | formats supported are `apache_allow`, `apache_deny`,`nginx_allow`,`nginx_deny`, `CIDR`, `linux_iptables`, `netmask`, `inverse_netmask`, `web_config_allow `, `web_config_deny`, `cisco_acl`, `peer_guardian_2`, `network_object`, `cisco_bit_bucket`, `juniper_junos`, `microtik`


## Response  details
The output formats supported are Nginx, Apache .htaccess, Linux iptables, CIDR, Netmask, Inverse Netmask, IIS web.config, Cisco ACL, PeerGuardian2, network-object, Cisco bit bucket, Juniper Junos and MicroTik. Please find the details below:

>  Response:

```
# -------------------------------------------------------
# Source: https://ipfinder.io/
# -------------------------------------------------------
# _____ ______   __  _             _
#|_   _|| ___ \ / _|(_)           | |
#  | |  | |_/ /| |_  _  _ __    __| |  ___  _ __
#  | |  |  __/ |  _|| || '_ \  / _` | / _ \| '__|
# _| |_ | |    | |  | || | | || (_| ||  __/| |
# \___/ \_|    |_|  |_||_| |_| \__,_| \___||_|
#
#______  _                             _  _
#|  ___|(_)                           | || |
#| |_    _  _ __  ___ __      __ __ _ | || |
#|  _|  | || '__|/ _ \ \ /\ / // _` || || |
#| |    | || |  |  __/ \ V  V /| (_| || || |
#\_|    |_||_|   \___|  \_/\_/  \__,_||_||_|
# -------------------------------------------------------
# [Important] Please update this list every month
# February 24, 2019, 8:24 pm
# Total ips: 74,240
# Download by ASN: AS2
# -------------------------------------------------------
add address=103.219.213.0/24 comment="AS2" list=IPfinder
add address=103.78.244.0/24 comment="AS2" list=IPfinder
add address=103.78.245.0/24 comment="AS2" list=IPfinder
add address=103.78.246.0/24 comment="AS2" list=IPfinder
add address=103.78.247.0/24 comment="AS2" list=IPfinder
add address=103.91.160.0/22 comment="AS2" list=IPfinder
add address=128.4.0.0/16 comment="AS2" list=IPfinder
add address=168.194.156.0/23 comment="AS2" list=IPfinder
add address=168.194.158.0/23 comment="AS2" list=IPfinder
add address=168.195.232.0/24 comment="AS2" list=IPfinder
add address=168.195.233.0/24 comment="AS2" list=IPfinder
add address=45.6.180.0/24 comment="AS2" list=IPfinder
add address=45.6.182.0/24 comment="AS2" list=IPfinder

....
....
....
....
....
....
```

Format                   | Sample Output
---------                |  -----------          |
`Apache .htaccess allow `| allow from 8.8.8.0/24 |
`Apache .htaccess deny  `| deny from 8.8.8.0/24  |
`Nginx allow`            | allow 8.8.8.0/24;     |
`Nginx deny`             | deny 8.8.8.0/24;      |
`CIDR`                   | 8.8.8.0/24            |
`Linux iptables `        | iptables -A INPUT -s 8.8.8.8/24 -j DROP  |
`Netmask`                | 8.8.8.0/255.255.255.0 |
`Inverse Netmask  `      | 8.8.8.0 0.0.0.255     |
`Web.config allow `      | `<ipSecurity allowUnlisted="false"><add ipAddress="8.8.8.0" subnetMask="255.255.255.0"/>` |
`Web.config deny  `      | `<ipSecurity allowUnlisted="true"><add ipAddress="8.8.8.0" subnetMask="255.255.255.0"/>` |
`Cisco ACL  `            | deny ip 8.8.8.0 0.0.0.255 any |
`PeerGuardian2  `        | HOST:8.8.8.0-8.255.255.255    |
`network-object `        | network-object 8.8.8.0 255.255.255.0 |
`Cisco bit bucket `      | ip route 8.8.8.0 255.255.255.0 Null0 |
`Juniper Junos  `        | set 8.8.8.0/24                       |
`MicroTik `              | add address=8.8.8.0/24 comment="Danger" list=MyList  |
