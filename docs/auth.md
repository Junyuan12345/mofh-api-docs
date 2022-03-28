---
title: Authentication
sidebar_position: 2
hide_table_of_contents: true
---
MOFH uses a API credential mechanism to allow access to the API. You can find them in your [MOFH Admin Panel](https://panel.myownfreehost.net/) or access them directly from [here](https://panel.myownfreehost.net/panel/index2.php?option=api).

MOFH requires API credentials to be included in all requests to the server. If a request doesn't include the credentials, the request will be rejected politely at all times.

## Shell Example
```shell
curl -X POST -u username:password "https://panel.myownfreehost.net/xml-api/"
```

## Python Example
```python
import requests

url = "https://panel.myownfreehost.net/xml-api/" # This is the base URL
data = {}

response = requests.post(url, params=data, auth=('username' 'password'), verify=False)
```

:::info

 You must replace `username` and `password` with your API credentials.

:::