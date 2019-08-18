# Errors

Whenever a requested resource is not available or an API call fails for another reason, a JSON error is returned. Errors always come with an error code and a description.




## Server
Server error codes:


Error Code | Meaning
---------- | -------
`400` | Bad Request -- Your request is invalid.
`401` | Unauthorized -- Your API key is wrong.
`403` | Forbidden -- The  requested is hidden for administrators only.
`404` | Not Found -- The specified  could not be found.
`405` | Method Not Allowed -- invalid method.
`406` | Not Acceptable -- You requested a format Not Acceptable .
`429` | Too Many Requests -- You're requesting too many ! Slow down!
`500` | Internal Server Error -- We had a problem with our server. Try again later.
`503` | Service Unavailable -- We're temporarily offline for maintenance. Please try again later.

## API
API error codes:


Error Code | Error id                   | Meaning
---------- | -------                    | -------
`104`      | usage_limit_reached        | You have reached your usage limit. Upgrade your plan if necessary.
`404`      | invalid_access_key         | No API Key was specified or an invalid API Key was specified.
`404`      | missing_token_key          | No API Key was specified.
`402`      | expired_paymant            | expired paymant please Upgrade your plan
`402`      | non_paymant                | non paymant Please Login to your dashbord and make order
`105`      | function_access_restricted | asn api note include in `basic` or `Free` acoount please Upgrade your plan
`405`      | method_not_allowed         | Method Not Allowed
`404`      | 404_not_found              | The requested resource does not exist.
