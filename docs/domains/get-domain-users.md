---
title: Get User By Domain
sidebar_position: 3
hide_table_of_contents: true
---
This endpoint gets a user which has the requested domain connected to their account which is available with the provided information. The following information is required while sending an request to the server:
- API Username (api credenital assigned to you)
- API Key (api credenital assigned to you)
- Subdomain (the domain to get the users info)

## HTTP Request
All API requests for this action must be made to `https://panel.myownfreehost.net/xml-api/getdomainuser.php`. Any other address for this action may result in an unknown error.

## Shell Request
```shell
curl -X POST -u username:password -d "api_user=username&api_key=password&domain=subdomain.example.com" "https://panel.myownfreehost.net/xml-api/getdomainuser.php"
```
## Python Request
```python
import requests
from requests.auth import HTTPBasicAuth

url = "https://panel.myownfreehost.net:2087/xml-api/getdomainuser.php"
data = {'api_user': 'username', 'api_key': 'password', 'domain': 'subdomain.example.com'}

response = requests.post(url, params=data, auth=HTTPBasicAuth('username', 'password'))

print(response.text)
```
### Array Response
```none
["ACTIVE","subdomain.example.com","\/home\/vol15_2\/example.com\/hname_12345678\/htdocs","hname_12345678"]
```