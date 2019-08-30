## JSONP/CORS Requests

JSONP and CORS are supported, allowing you to use ipfinder.io entirely in client-side code. For JSONP you just need to specify the callback parameter, e.g. https://api.ipfinder.io/v1/1.0.0.0?token=free&format=jsonp&callback=callback. Most javascript libraries will automatically handle this for you though.

Here's a jQuery example that logs the client IP and country:

```javascript
$.get("https://api.ipfinder.io/v1/1.0.0.0?token=free", function(response) {
  console.log(response.ip, response.country_code);
}, "jsonp")
```
