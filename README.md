# python-console-keycloak-example

A client application, configured as an OIDC client in [Keycloak](https://www.keycloak.org/) that shows how to obtain access grants, using the OAuth's [Resource Owner Password Credentials](https://tools.ietf.org/html/rfc6749#section-1.3.3)


#### Keycloak configuration (if not done already)

Create a new OIDC client in keycloak, with "Access Type" set to "confidential" and optionally disable the option "Standard Flow Enabled" and save it.
Click again on the client and go under Credentials tab, you will see the secret.

## Usage
Copy `keycloak.json.template` to `keycloak.json` or to any filename of your choice and change the values according to your environment.
If the filename is different than `keycloak.json`, pass the filename as argument. 
```shell
python KCAuth.py <filename>
```

## Developers
Usage of the library
```python
from KCAuth import KCAuth

kcAuth = KCAuth("keycloak.json")
kcAuth.getAccessToken()
```

## Curl usage

```shell
#Use the access token as follows
ACCESS_TOKEN=<copy-your-access-token-from-the-python-script>
RESOURCE_URL=http://localhost:8080/my-protected-resource
curl -H "Authorization: Bearer $ACCESS_TOKEN" $RESOURCE_URL
```
