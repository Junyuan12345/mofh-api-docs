---
title: Domain Availability
sidebar_position: 1
hide_table_of_contents: true
---
This endpoint will check if the requested domain is available with the provided information. The following information is required while sending an request to the server:
- API Username (api credenital assigned to you)
- API Key (api credenital assigned to you)
- Subdomain (the domain choosen by the client)

## HTTP Request
All API requests for this action must be made to `https://panel.myownfreehost.net/xml-api/checkavailable.php`. Any other address for this action may result in an unknown error.

## Shell Request
```shell
curl -X POST -u username:password -d "api_user=username&api_key=password&domain=subdomain.example.com" "https://panel.myownfreehost.net/xml-api/checkavailable.php"
```
## Python Request
```python
import requests
from requests.auth import HTTPBasicAuth

url = "https://panel.myownfreehost.net/xml-api/checkavailable.php"
data = {'api_user': 'username', 'api_key': 'password', 'domain': 'subdomain.example.com'} # If you want to use a domain which is not a subdomain, put that domain in.

response = requests.post(url, params=data, auth=HTTPBasicAuth('username', 'password'))

print(response.text) # Returns the status code, either 0 or 1.
```
### XML Response
```xml
1
```