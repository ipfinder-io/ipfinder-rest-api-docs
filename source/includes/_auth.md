# Authentication

> In order to fetch information about an IP address, you need to build a request URL of the following form :



```shell
# With token query parameter

$ curl -X GET /
     https://api.ipfinder.io/v1/?token=$TOKEN 

# With POST application/json

$ curl -d '{"token":"$TOKEN"}' \
       -H "Content-Type: application/json" \
       -X POST https://api.ipfinder.io/v1/

# With POST application/x-www-form-urlencoded

$ curl -d "token=$TOKEN" \
       -H "Content-Type: application/x-www-form-urlencoded" \
       -X POST https://api.ipfinder.io/v1/

# With Basic Auth
$ curl -u $TOKEN: https://api.ipfinder.io/v1/

# With X-Authorization token
$ curl -H 'X-Authorization: $TOKEN' https://api.ipfinder.io/v1/
```

```php
<?php 
use ipfinder\ipfinder\IPfinder;

// Token
$client = new IPfinder('YOUR_TOKEN_GOES_HERE');


// lookup your IP address information

$details = $client->Authentication();

var_dump($details);

```

```python
import ipfinder

config = ipfinder.config('YOUR_TOKEN_GOES_HERE')

# lookup your IP address information
auth = config.Authentication()

auth.details
```

```javascript
const Ipfinder = require('ipfinder');
const ipfinder = new Ipfinder('YOUR_TOKEN_GOES_HERE');

ipfinder.Authentication().then(data => {
     console.log(data);
    // console.log(data.status_message);
}).catch(console.log);
```

```ruby
require 'ipfinder'
config = Ipfinder::config('YOUR_TOKEN_GOES_HERE')

# lookup your IP address information
puts auth.inspect

puts auth.ip # your ip
```
```java
        Ipfinder ipfinder = new Ipfinder("YOUR_TOKEN_GOES_HERE", ""); 

        try {
            // lookup your IP address information
            IPResponse response = ipfinder.authentication();
            
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

accconf Ipfinder:init("YOUR_TOKEN_GOES_HERE")

-- lookup your IP address information
auth = conf:Authentication()

print(inspect(auth))
```

```d
        Ipfinder ipfinder = new Ipfinder("YOUR_TOKEN_GOES_HERE");

        try {
            // lookup your IP address information
            JSONValue response = ipfinder.authentication();

            writeln(response);

            // print city name
            writeln(response.getCity());

        } catch (Exception e) {
            // Handle error
        }
```

```r
require(ipfinder)

accconf Ipfinder(token="YOUR_TOKEN_GOES_HERE")

# lookup your IP address information
auth <- Authentication(conf)

auth
# print your ip
auth$ip
```

```elixir
iex> conf = Ipfinder.new("YOUR_TOKEN_GOES_HERE")

# lookup your IP address information
iex> {:ok, auth} = Authentication(conf)

iex> auth
# print your ip
iex> auth.ip
```

```swift
import ipfinder

let ipfinder = Ipfinder("YOUR_TOKEN_GOES_HERE")

// lookup your IP address information
let auth = ipfinder.Authentication()

print(auth)
```

```go 
// lookup your IP address information
func main() {
  conf := ipfinder.New("YOUR_TOKEN_GOES_HERE", "")
  auth, err := conf.Authentication()

  if err != nil {
    fmt.Println("Error : ", err)
  } else {
    fmt.Println(auth)
  }
}
```

```powershell

  # shortopt
$ ipfinder -a 
  # longopt
$ ipfinder --auth 

```

> Make sure to replace `$TOKEN` with your API key.

Your API token is used to authenicate you with our API, and can be provided either as a  `POST` , `Basic Auth` OR `X-Authorizatio`, or alternatively as a token URL parameter.



<aside class="notice">
You must replace <code>$TOKEN</code> with your personal API key.
</aside>
<aside class="success">
Note Api key <code>$TOKEN</code> Work in all project
</aside>
