## HTTPS / SSL

Our API is available over a secure HTTPS connection for all users, even on the free plan. Simply add ```https://``` to the request URLs to make the requests secure.

````bash
# Get details for your own IP address over HTTPS
$ curl https://api.ipfinder.io/v1/?token=$TOKEN
````
