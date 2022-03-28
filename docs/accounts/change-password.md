---
title: Change Password
sidebar_position: 4
hide_table_of_contents: true
---
This endpoint will reset the password of an existing free hosting account with the provided information. The following information is required while sending an request to the server:
- Username (domain prefix with an 8 digit number)
- Password (the new password for the username)

## HTTP Request
All API requests for this action must be made to `POST https://panel.myownfreehost.net/xml-api/passwd.php`. Any other address for this action may result in an unknown error.

## Shell Request
```shell
curl -X POST -u username:password -d "user=username&pass=password" "https://panel.myownfreehost.net/xml-api/passwd.php"
```
## Python Request
```python
import requests
from requests.auth import HTTPBasicAuth
# from xml.etree.ElementTree import fromstring, ElementTree - Do this if you want to only get the status code.

url = "https://panel.myownfreehost.net:2087/xml-api/passwd.php"
data = {'user': 'username', 'pass': 'password'} # For the username, use the same username you set when creating the account.

response = requests.post(url, params=data, auth=HTTPBasicAuth('username', 'password'))

print(response.text)

# tree = ElementTree(fromstring(response.content)) - Do this if you want to only get the status code.
# root = tree.getroot() - Do this if you want to only get the status code.
# for child in root: - Do this if you want to only get the status code.
#  print(child[5].text) # The status code (can either be 0 or 1) - Do this if you want to only get the status code.
```
### XML Response
```xml
<passwd>
        <passwd>
                <rawout>        
                 Changing password for username
                 Password for username has been changed 
                 Updating ftp passwords for username
                 Ftp password files updated. 
                 Ftp vhost passwords synced
                </rawout>
                 <services>
                      <app>system</app>
                 </services>
                 <services>
                      <app>ftp</app>
                 </services>
                 <services>
                      <app>mail</app>
                 </services>
                 <services>
                       <app>mySQL</app>
                 </services>
                <status>1</status>
                <statusmsg>Password changed for user username</statusmsg>
        </passwd>
</passwd>
```