---
title: Unsuspend Account
sidebar_position: 3
hide_table_of_contents: true
---
This endpoint will unsuspend an already suspended free hosting account with the provided information. The following information is required while sending an request to the server:
- Username (domain prefix with an 8 digit number)
- Password (the password for the username)

## HTTP Request
All API requests for this action must be made to `POST https://panel.myownfreehost.net/xml-api/unsuspendacct.php`. Any other address for this action may result in an unknown error.

## Shell Request
```shell
curl -X POST -u username:password -d "user=username" "https://panel.myownfreehost.net/xml-api/unsuspendacct.php"
```
## Python Request
```python
import requests
from requests.auth import HTTPBasicAuth
# from xml.etree.ElementTree import fromstring, ElementTree - Do this if you want to only get the status code.

url = "https://panel.myownfreehost.net/xml-api/unsuspendacct.php"
data = {'user': 'username'} # For the username, use the same username you set when creating the account.

response = requests.post(url, params=data, auth=HTTPBasicAuth('username', 'password'))

print(response.text)

# tree = ElementTree(fromstring(response.content)) - Do this if you want to only get the status code.
# root = tree.getroot() - Do this if you want to only get the status code.
# for child in root: - Do this if you want to only get the status code.
#  print(child[0].text) # The status code (can either be 0 or 1) - Do this if you want to only get the status code.
```
### XML Response
```xml
<unsuspendacct>
    <result>
        <status>1</status>
        <statusmsg>
            <script>if (self['clear_ui_status']) { clear_ui_status(); }</script>
            username account has been unsuspended
        </statusmsg>
    </result>
</unsuspendacct>
```