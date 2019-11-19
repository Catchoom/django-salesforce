I did get it to work by just hitting more docs and trying more stuff.

First request--

```
https://login.salesforce.com/services/oauth2/authorize
client_id:xyzzyg9rbsTkKnAUNPxvJNeDie.vUg87NuTTB.SAwQBUkFfw3_vXwR0LD3jeWm1GUUX9COwnESvMOYcF4Z8j2
response_type:code
redirect_uri:https://timetrade.com/whatIsTheURL
scope:refresh_token
```

That will give you an HTML page with a login to SF.  When you use the URL in that page to login and grant access to the app, it redirects to --

https://www.timetrade.com/whatIsTheURL?code=xyzzybOND3gL_2LanWKqJr2UGrUxYj_QyF0wyEv6_uVXY5wxc6qAXFovCO1C_.6H3wui9y4dBLQ%3D%3D

With that code you do another request--

```
https://login.salesforce.com/services/oauth2/token
client_id:xyzzyg9rbsTkKnAUNPxvJNeDie.vUg87NuTTB.SAwQBUkFfw3_vXwR0LD3jeWm1GUUX9COwnESvMOYcF4Z8j2
grant_type:authorization_code
redirect_uri:https://timetrade.com/whatIsTheURL
client_secret:xyzzy53467474526263
code:xyzzybOND3gL_2LanWKqJr2UGrUxYj_QyF0wyEv6_uVXY5wxc6qAXFovCO1C_.6H3wui9y4dBLQ==
```

%3D translated to =
That will return--
```
{
    "access_token": "xyzzyI00000046ll!ARMAQLJQnFOduGakfOPiuxCXSGr4jPK7RAMvJf79eHmazSi5aTK2F0CUafgClw.vJ_j_29kQDHn1z7EjJdlAQEON_qiMzEL7",
    "refresh_token": "xyzzy1hJJeETRTRP.QYd3Mbpt2P8_VFHWV3gHGnIXdELcjiQe_.IERkQHLUQaRH_Yjw_GlgsCtlD8sj72YuneL",
    "signature": "JTpuGvoRuLxCFgWeVGvAUR9zNwFUCzGYPxfYnK1l3/U=",
    "scope": "refresh_token",
    "instance_url": "https://ttkkcatdev-dev-ed.my.salesforce.com",
    "id": "https://login.salesforce.com/id/00D1I00000046llUAA/0051I000000hAq6QAE",
    "token_type": "Bearer",
    "issued_at": "1532639189188"
}
```
