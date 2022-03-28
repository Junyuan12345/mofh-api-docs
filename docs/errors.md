---
title: Errors
sidebar_position: 5
hide_table_of_contents: true
---
The MOFH API doesn't return any error codes, and will always return a `200` HTTP code for any request.

You would have to get the text inside the `<status>` `</status>` tags to get the status of your request (either `0` or `1`). Or if you try to use the `getuserdomains.php` and `getdomainuser.php` endpoints you will see that it just returns `NULL` instead of the list/array it usually gives.