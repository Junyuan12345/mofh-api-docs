---
title: Create Account
sidebar_position: 1
hide_table_of_contents: true
---
This endpoint will create a new free hosting account with the provided information. The following information is required while sending an request to the server:
- Username (domain prefix with an 8 digit number)
- Password (a random password sixteen digit password)
- Email (the client's email address)
- Subdomain (the domain choosen by the client)
- Plan (custom service quota plan, leave empty if none)

## HTTP Request
All API requests for this action must be made to `https://panel.myownfreehost.net/xml-api/createacct.php`. Any other address for this action may result in an unknown error.

## Shell Request
```shell
curl -X POST -u username:password -d "username=example&password=password&contactemail=example@example.com&domain=subdomain.example.com&plan=MyAwesomePlan" "https://panel.myownfreehost.net/xml-api/createacct.php"
```
## Python Request
```python
import requests
from requests.auth import HTTPBasicAuth
# from xml.etree.ElementTree import fromstring, ElementTree - Do this if you want to only get the username.

url = "https://panel.myownfreehost.net/xml-api/createacct.php"
data = {'username': 'example', 'password': 'password', 'contactemail': 'example@example.com', 'domain': 'subdomain.example.com', 'plan': 'MyAwesomePlan'} # If you want to use a domain which is not a subdomain, put that domain in.

response = requests.post(url, params=data, auth=HTTPBasicAuth('username', 'password'))

print(response.text)

# tree = ElementTree(fromstring(response.content)) - Do this if you want to only get the username.
# root = tree.getroot() - Do this if you want to only get the username.
# for child in root: - Do this if you want to only get the username.
#  print(child[0][1].text) # The vPanel and FTP username - Do this if you want to only get the username.
```
### XML Response
```xml
<createacct>
	<result>
		<options>
			<ip>n</ip>
			<vpusername>hname_12345678</vpusername>
			<nameserver>ns1.byet.org</nameserver>
			<nameserver2>ns2.byet.org</nameserver2>
			<nameserver3/>
			<nameserver4/>
			<nameservera/>
			<nameservera2/>
			<nameservera3/>
			<nameservera4/>
			<nameserverentry/>
			<nameserverentry2/>
			<nameserverentry3/>
			<nameserverentry4/>
			<package></package>
		</options>
		<rawout>
           account added to queue to be added 
            </rawout>
		<status>1</status>
		<statusmsg>This account has been successfuly created</statusmsg>
	</result>
</createacct>
```