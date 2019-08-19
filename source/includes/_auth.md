# Authentication

> In order to fetch information about an IP address, you need to build a request URL of the following form :



```shell
# With token query parameter

$ curl -X GET /
     https://api.ipfinder.io/v1/?token=$TOKEN 

# With POST application/json

$ curl -d '{"token":"$TOKEN"}' /
       -H "Content-Type: application/json" /
       -X POST /
       https://api.ipfinder.io/v1/

# With POST application/x-www-form-urlencoded

$ curl -d "token=$TOKEN" /
       -H "Content-Type: application/x-www-form-urlencoded" /
       -X POST /
       https://api.ipfinder.io/v1/

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

> Make sure to replace `$TOKEN` with your API key.

Your API token is used to authenicate you with our API, and can be provided either as a  `POST` , `Basic Auth` OR `X-Authorizatio`, or alternatively as a token URL parameter.



<aside class="notice">
You must replace <code>$TOKEN</code> with your personal API key.
</aside>
<aside class="success">
Note Api key <code>$TOKEN</code> Work in all project
</aside>
