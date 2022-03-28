---
title: Suspend Account
sidebar_position: 2
hide_table_of_contents: true
---
This endpoint will suspend an existing free hosting account with the provided information. The following information is required while sending an request to the server:
- Username (domain prefix with an 8 digit number)
- Reason (a valid reason for suspending)

## HTTP Request
All API requests for this action must be made to `https://panel.myownfreehost.net/xml-api/suspendacct.php`. Any other address for this action may result in an unknown error.

## Shell Request
```shell
curl -X POST -u username:password -d "user=example&reason=My beautiful reason." "https://panel.myownfreehost.net/xml-api/suspendacct.php"
```
## Python Request
```python
import requests
from requests.auth import HTTPBasicAuth
# from xml.etree.ElementTree import fromstring, ElementTree - Do this if you want to only get the status code.

url = "https://panel.myownfreehost.net/xml-api/suspendacct.php"
data = {'user': 'username', 'reason': 'My beautiful reason.'} # For the username, use the same username you set when creating the account.

response = requests.post(url, params=data, auth=HTTPBasicAuth('username', 'password'))

print(response.text)

# tree = ElementTree(fromstring(response.content)) - Do this if you want to only get the status code.
# root = tree.getroot() - Do this if you want to only get the status code.
# for child in root: - Do this if you want to only get the status code.
#  print(child[0].text) # The status code (can either be 0 or 1) - Do this if you want to only get the status code.
```
### XML Response
```xml
<suspendacct>
    <result>
        <status>1</status>
        <statusmsg>
            <script>if (self['clear_ui_status']) { clear_ui_status(); }</script>
            Changing Shell to /bin/false...Changing shell for username.
            Shell changed.
            Locking Password...Locking password for user username.
            marking user vhosts / databases for suspension.
            ..
            ..
            Completed, this account will be fully suspended in 2 minutes.
        </statusmsg>
    </result>
</suspendacct>
```