---
comments: true
---

The ZTAA platform provides support for API based authentication. Built on the OAuth2.0 framework, the APIs can be leveraged to provide Single Sign On (SSO) to non-SAML web applications.

The workflow for utilizing the authentication APIs are as follows:

1. Create a OAuth2 profile in the ZTAA admin console to generate the client id & client secret.

2. Create a SSO profile in the ZTAA admin console to bind the OAuth2 profile with the users/user groups who needs to be validated for authentication.

3. The /token api from the ZTAA platform to be invoked to generate an access token based on the client id & client secret.

4. The /login api from the ZTAA platform which takes the input as the username, password and generated access token to authenticate the user.

### Creating a OAuth2 profile
1. Click on the Configuration button on the left side menu.
2. Click on the OAuth-2 tab on the top menu.
3. Click on the '+' icon to create a new OAuth2 profile and provide a name.
4. Click on the 'Generate Client Credential' button.
5. The OAuth2 profile is created and a text file containing the client id and client secret is downloaded.

Note: The client id and client secret is available for a one-time download and should be saved securely.

### Create a SSO API Identity Provider profile
1. Click on the Identity Management button on the left side menu.
2. Click on the Identity Provider tab on the top menu.
3. Click on the '+' icon and click on the 'SSO API' icon.
4. Give a IDP name and click on the Submit button.
5. Click on the created SSO IDP and click on the Edit button.
6. Click on the User Credentials tab inside the SSO IDP profile.
7. Click on the '+' icon and search for the OAuth profile which needs to be associated with the SSO IDP profile and select it.
8. Click on the 'User/User Group' tab and select the users/user group who needs to be authenticated.

The below video shows the steps for creating a OAuth2 profile and SSO API Identity Provider.

![SSO_API](../static/ztaa/OAuth2.gif)

### Generate access token

The /token api from the ZTAA platform is to be invoked to generate an access token. The details of the api are given below:

```
POST https://<tenant url>/console/g2/oauth2/token

Request Headers
Accept: */*
Cache-Control: no-cache
Connection: keep-alive
Content-Type: multipart/form-data; 

Request Body
 
grant_type: "client_credentials"
 
client_id: "<generated client id>"
 
client_secret: "<generated client secret>"
 
scope: "all"


Response Body

{
  "access_token": "NDI1NDVMNWMTZTLHZS0ZMTDHLTG2NJKTODLHY2E3ZTLLYWY4",
  "expires_in": 86400,
  "refresh_token": "ZTA4OGYWZMYTODM4OS01MZZLLTGWYMYTMJM0OWVJMZE3YZCY",
  "scope": "all",
  "token_type": "Bearer"
}

```

### Authenticate users 

The /login api from the ZTAA platform is to be invoked to authenticate users. The details of the api are given below:

```
POST https://<tenant url>/console/g2/sso/login

Request Headers
Content-Type: application/json
Authorization: Bearer NDI1NDVMNWMTZTLHZS0ZMTDHLTG2NJKTODLHY2E3ZTLLYWY4
Accept: */*
Connection: keep-alive

Request Body

{
    "username" : "<username>", 
    "password" : "<password>" 
}

Response Body

{
  "timestamp": "2024-01-02 11:56:29.190889139 +0000 UTC m=+345456.289388074",
  "statusCode": 200,
  "errorCode": 0,
  "errorSubCode": 0,
  "data": {
    "authenticated": true,
    "sessionExpiry": "1704556589",
    "message": "user authentication successful",
    "attributes": {
      "role": "4",
      "userName": "username"
    }
  },
  "errorData": "",
  "success": true
}
```

