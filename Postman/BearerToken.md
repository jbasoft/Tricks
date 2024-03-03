This is Sample PreCode for get auth bearer token before send request in POSTMAN

*Add this code in prerequest
```
var authServiceUrl = pm.environment.get('TOKEN_URL');
var cname = pm.environment.get('UNAME');
var cpword = pm.environment.get('PWD_ENCRYPTED');

pm.sendRequest({
    url: authServiceUrl,
    method: 'POST',
header: 'Content-Type:application/x-www-form-urlencoded',
  body: {
            mode: 'urlencoded',
            urlencoded: [
                    { key: "username", value: 'cname' },
                    { key: "password", value: 'cpword' },
            ]
    }
    });
```
**And add TOKEN_URL, UNAME, PWD_ENCRYPTED in your environment 
