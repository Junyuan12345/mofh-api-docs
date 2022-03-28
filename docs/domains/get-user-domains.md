---
title: Get User Domains
sidebar_position: 2
hide_table_of_contents: true
---
This endpoint will get the domains connected to a user's account which is available with the provided information. The following information is required while sending an request to the server:
- API Username (api credenital assigned to you)
- API Key (api credenital assigned to you)
- Username (the account username of the client)

## HTTP Request
All API requests for this action must be made to `https://panel.myownfreehost.net/xml-api/getuserdomains.php`. Any other address for this action may result in an unknown error.

## Shell Request
```shell
curl -X POST -u username:password -d "api_user=username&api_key=password&username=hname_12345678" "https://panel.myownfreehost.net/xml-api/getuserdomains.php"
```
## Python Request
```python
import requests
from requests.auth import HTTPBasicAuth

url = "https://panel.myownfreehost.net/xml-api/getuserdomains.php"
data = {'api_user': 'username', 'api_key': 'password', 'username': 'hname_12345678'}

response = requests.post(url, params=data, auth=HTTPBasicAuth('username', 'password'))

print(response.text)
```
### Array Response
```none
[["ACTIVE","subdomain.example.com"]]
```