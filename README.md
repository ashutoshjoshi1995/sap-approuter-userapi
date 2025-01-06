# User API in @sap/approuter

The api is useful to retrieve the user information in any application deployed on BTP. It could be a Fiori, NodeJs, CAP, etc application. 

## Summary

- Refers to [@sap/approuter](https://www.npmjs.com/package/@sap/approuter)
- minimal config added - `package.json`, `xs-app.json` and `xs-security.json`
- Highlights to be noted - minimal config, addition of redirect URI in xs-security.json


## Usage
Create the XSUAA service in BTP CF using:

`cf create-service xsuaa application user-api-uaa -c xs-security.json`

Push the Application to CF using:

`cf push`  

It would consider the manifest.yml file for app creation and bind the xsuaa service

Use the following link to view the user information: 

`
https://sap-approuter-userapi-humble-vicuna-ic.cfapps.us10-001.hana.ondemand.com/user-api/currentUser
`

### Example Response:
```json

{
    firstname: "Ashutosh",
    lastname: "Joshi",
    email: "ashutosh-joshi@abc.com",
    name: "ashutosh-joshi@abc.com",
    scopes: [
        "openid"
    ],
    displayName: "Ashutosh Joshi (ashutosh-joshi@abc.com)"
}

```
